---
createdAt: 2021-12-19T23:00:00.000+00:00
title: React `useImperativeHandle` Magic
short_description: How useImperativeHandle + useCallback + useState works together.
author: src/data/forestry/content/authors/artur-czemiel.md
category: ""
first_category: Frontend
second_category: React JS
third_category: TypeScript
feature_image: "/uploads/react-js-hooks.png"
---

## Intro

I am a full-stack TypeScript developer and I've been learning the Elm language a lot recently. Will I switch to Elm? Definitely not. However, the learning process helped me understand and demand more things in React.

Today I will show you a React anti-pattern that will allow you to **share state outside components**. Why would you do this? Why not use a hook? etc. etc. I will show you an example with a small form.

**Note:** This is not a "real-world" example. In production env I am using this hook to create a synchronized S3 File browser, but it might be too much for the sake of this article.

## The hook

So this combination of State and Callback is to connect the ref function later and listen when the ref changes:

```tsx
import { useState, useCallback } from "react";

export const useImperativeRef = <T,>() => {
  const [refState, setRefState] = useState<T>();
  const ref = useCallback((n: T | null) => {
    if (n) {
      setRefState(n);
    }
  }, []);
  return [refState, ref] as const;
};
```

## The form

We don't need anything fancy for this example so we will use a simple form with 2 inputs:

```tsx
import React, { useImperativeHandle, useState } from "react";

interface FormValues {
  username: string;
  password: string;
}

export interface MyFormHandle {
  values: FormValues;
}

export const MyForm = React.forwardRef(
  ({}, ref: React.ForwardedRef<MyFormHandle>) => {
    const [values, setValues] = useState<FormValues>({
      username: "",
      password: "",
    });
    useImperativeHandle(ref, () => ({
      values,
    }));
    return (
      <div>
        <input
          type="text"
          value={values.username}
          onChange={(e) =>
            setValues({
              ...values,
              username: e.target.value,
            })
          }
        />
        <input
          type="password"
          value={values.password}
          onChange={(e) =>
            setValues({
              ...values,
              password: e.target.value,
            })
          }
        />
      </div>
    );
  },
);
```

## Using the form

Et voila! We can listen to state changes of components underneath:

```tsx
export default () => {
  const [values, setRef] = useImperativeRef<MyFormHandle>();
  useEffect(() => {
    console.log(`Values changed!, Values: ${JSON.stringify(values, null, 4)}`);
  }, [values]);
  return (
    <div>
      <MyForm ref={setRef} />
    </div>
  );
};
```

Of course, we can pass change functions and values, but let's be true - that's Yuck! In my opinion, this way is much more elegant and codeless in many cases.
