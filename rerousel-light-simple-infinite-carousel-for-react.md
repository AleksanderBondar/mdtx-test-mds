---
author: src/data/forestry/content/authors/tomek-poniatowicz.md
first_category: React JS
second_category: Frontend
third_category: Web
feature_image: "/uploads/react-js-hooks-1.png"
createdAt: 2022-03-02T08:00:00Z
title: Rerousel - simplest carousel for React
short_description: Carousels or image sliders have been always used for enhancing
  the visual appeal of websites, presenting products, customers or testimonials. Let's
  take a look at Rerousel, the simplest infinite carousel for React.

---
Modularity and reusability are among the principles of React. React components are independent and reusable pieces of code that are responsible for one specific thing. This approach helps to keep the code clean and elegant. **Rerousel** is the simplest and lightest infinite carousel component package created for React, with the goal of providing a way to show that your application follows these principles:

* **Simple** - Carousel setup is very easy, just install the package and import Rerousel and the component setup is effortless,
* **Lightweight** - Rerousel is the lightest working React JS infinite carousel available for download from NPM. It uses only the packages that are necessary, so you don't have to worry about thousands of excessive dependencies flooding your app,
* **Versatile** - It doesn't matter if you are building an eCommerce app for businesses and need to showcase your products or a personal project to display your vacation photos - Rerousel is for you. It supports all JSX element types, so you don't have to worry about compatibility.

## How to use it

Install the package using npm:
```
    npm install rerousel
```
Then import Rerousel into your React project:
```tsx
    import { Rerousel } from 'rerousel';
```

Place it in your app and populate with the items you want to showcase, create a ref pointing at your outermost item and include it in the **Rerousel** as itemRef prop.

```tsx
    export const Component: React.FC<CustomersProps> = ({ customers }) => {
        const customerLogo = useRef(null);
    
        return (
            <Container>
                <Rerousel itemRef={customerLogo}>
                    {customers.map((c) => {
                        return <Img key={c.image} image={c.image} ref={customerLogo} />;
                    })}
                </Rerousel>
            </Container>
        );
    };

```

Et voila! Enjoy the simplest, the lightest & the most reliable infinite carousel package made for React. If you want to get more info on it make sure to visit [Rerousel's repo on GitHub](https://github.com/aexol-studio/rerousel).