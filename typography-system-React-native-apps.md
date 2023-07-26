---
createdAt: 2023-04-28T16:00:00.000+00:00
title: How to create a React Native typography system
short_description: A guide on how to create a React Native typography system for use in all applications including a monorepo and those for Android and iOS.
author: src/data/forestry/content/authors/marcin.md
category: ""
first_category: React Native
second_category: Frontend
third_category: TypeScript
feature_image: "/uploads/Marcin_blogpost.png"
---

Reducing boilerplate code and minimizing code repetition is something all developers pay close attention to in their projects. Same with the ease of use of all the various tools, as they are designed to save time and that’s exactly what I’ll try to show in this tutorial!

We’ll get to know how to properly install and handle fonts in iOS and Android, and create an easy and intuitive typography system that will save time and reduce the amount of code when developing both Single and Monorepo apps. It doesn't matter if your app has a lot of text or not - this solution will work great for either. Most importantly, the system we will create will be based on font type, size and weight. This will let us build fully editable custom components, which means we’ll have a lot more possibilities in the styling of our app.

```ts
<Text style={{...typographySystem.yourFont, other styles}}>Your text</Text>
```

1. Settings

I use `Yarn`. If you're using `NPM`, don't worry - it will be very similar.

2. `.ttf` files

Download the font files using for example: `google fonts`. For this article, I’ll be using a "Poppins" font.

3. Fonts directory

After downloading, create a `fonts` directory in your `assets` folder. Move all the font files into this fonts directory. The path to your font files should look like this:

- **Single app**
  `my-app/src/assets/fonts`
- **Monorepo apps**
  `mono-repository/packages/shared/src/assets/fonts`

#### **Create a `index.ts` file to create and export const your font files.**

In your `fonts` directory create a `index.ts` file. It should look like this:

```ts
export const PRIMARY_FONT_REGULAR = "Poppins-Regular";
export const PRIMARY_FONT_SEMI = "Poppins-SemiBold";
export const PRIMARY_FONT_BOLD = "Poppins-Bold";
export const PRIMARY_FONT_THIN = "Poppins-Thin";
export const PRIMARY_FONT_MEDIUM = "Poppins-Medium";
export const PRIMARY_FONT_LIGHT = "Poppins-Light";
export const PRIMARY_FONT_EXTRALIGHT = "Poppins-ExtraLight";
export const PRIMARY_FONT_EXTRABOLD = "Poppins-ExraBold";
export const PRIMARY_FONT_BLACK = "Poppins-Black";
```

> For prettier paths, you can create an index.ts file in your assets folder. The body of this file should be something like this: `export * from "./fonts";`

#### App configuration

Create a `react-native.config.js` file in the root directory of your project. If you are working with a monorepo, please do this for every app in it.

### Example folder structure:

**Single app**

```
  my-app/
    src/
        assets/
         index.ts
            fonts/
                index.ts
                fontFile.ttf
    react-native.config.js
```

**Monorepo**

```
  my-monorepo/
    packages/
        app1/
            react-native.config.js
        app2/
            react-native.config.js
        shared/
            src/
                assets/
                    index.ts
                    fonts/
                        index.ts
                        fontFile.ttf
```

Now edit your `react-native.config.js` file to add the assets path. It should be something like this:

**Single app**

```js
module.exports = {
  project: {
    ios: {},
    android: {},
  },
  assets: ["./src/assets/fonts/"],
};
```

**Monorepo**

```js
module.exports = {
  project: {
    ios: {},
    android: {},
  },
  assets: ["../../node_modules/@my-monorepo/shared/src/assets"],
};
```

#### **Creating the typography system**

Now, we can create a typography system. In your `src` directory, create a new folder named `styles`. Inside this folder create a `typographySystem.ts` file.

> For a monorepo do this in your `shared` package directory.

In this file, we can now import our exported consts of fonts, like so:

```ts
import {
  PRIMARY_FONT_BOLD,
  PRIMARY_FONT_SEMI,
  PRIMARY_FONT_REGULAR,
  PRIMARY_FONT_MEDIUM,
} from "@/assets/fonts";
```

> I have absolute imports in my project so bear in mind your 'from' path can be different!

I would also like to use a `StyleSheet` so, let's import it as well:

```ts
import { StyleSheet } from "react-native";
```

> Please, check your import path. Automatic import may be from 'react-native/types' and cause errors!

Now that we have imports, we can create our typographySystem StyleSheet which we will use in our projects! Here's my file as an example:

```ts
import {
  PRIMARY_FONT_BOLD,
  PRIMARY_FONT_SEMI,
  PRIMARY_FONT_REGULAR,
  PRIMARY_FONT_MEDIUM,
} from "@/assets/fonts";
import { StyleSheet } from "react-native";

export const typographySystem = StyleSheet.create({
  H3Bold: {
    fontFamily: PRIMARY_FONT_BOLD,
    fontSize: 24,
  },
  H3Semi: {
    fontFamily: PRIMARY_FONT_SEMI,
    fontSize: 24,
  },
  H3Medium: {
    fontFamily: PRIMARY_FONT_MEDIUM,
    fontSize: 24,
  },
  H2Bold: {
    fontFamily: PRIMARY_FONT_BOLD,
    fontSize: 22,
  },
  H2Semi: {
    fontFamily: PRIMARY_FONT_SEMI,
    fontSize: 22,
  },
  H2Medium: {
    fontFamily: PRIMARY_FONT_MEDIUM,
    fontSize: 22,
  },
  H1Bold: {
    fontFamily: PRIMARY_FONT_BOLD,
    fontSize: 20,
  },
  H1Semi: {
    fontFamily: PRIMARY_FONT_SEMI,
    fontSize: 20,
  },
  H1Medium: {
    fontFamily: PRIMARY_FONT_MEDIUM,
    fontSize: 20,
  },
  subtitle1Bold: {
    fontFamily: PRIMARY_FONT_BOLD,
    fontSize: 18,
  },
  subtitle1Semibold: {
    fontFamily: PRIMARY_FONT_SEMI,
    fontSize: 18,
  },
  subtitle1Medium: {
    fontFamily: PRIMARY_FONT_MEDIUM,
    fontSize: 18,
  },
  subtitle1Regular: {
    fontFamily: PRIMARY_FONT_REGULAR,
    fontSize: 18,
  },
  body1Semibold: {
    fontFamily: PRIMARY_FONT_SEMI,
    fontSize: 16,
  },
  body1Medium: {
    fontFamily: PRIMARY_FONT_MEDIUM,
    fontSize: 16,
  },
  body1Regular: {
    fontFamily: PRIMARY_FONT_REGULAR,
    fontSize: 16,
  },
  body2Semibold: {
    fontFamily: PRIMARY_FONT_SEMI,
    fontSize: 14,
  },
  body2Medium: {
    fontFamily: PRIMARY_FONT_MEDIUM,
    fontSize: 14,
  },
  body2Regular: {
    fontFamily: PRIMARY_FONT_REGULAR,
    fontSize: 14,
  },
  caption1Semibold: {
    fontFamily: PRIMARY_FONT_SEMI,
    fontSize: 12,
  },
  caption1Medium: {
    fontFamily: PRIMARY_FONT_MEDIUM,
    fontSize: 12,
  },
  caption1Regular: {
    fontFamily: PRIMARY_FONT_REGULAR,
    fontSize: 12,
  },
  caption2Semibold: {
    fontFamily: PRIMARY_FONT_SEMI,
    fontSize: 11,
  },
  caption2Medium: {
    fontFamily: PRIMARY_FONT_MEDIUM,
    fontSize: 11,
  },
  caption2Regular: {
    fontFamily: PRIMARY_FONT_REGULAR,
    fontSize: 11,
  },
  tooltipSemi: {
    fontFamily: PRIMARY_FONT_SEMI,
    fontSize: 10,
  },
  tooltipMedium: {
    fontFamily: PRIMARY_FONT_MEDIUM,
    fontSize: 10,
  },
  tooltipRegular: {
    fontFamily: PRIMARY_FONT_REGULAR,
    fontSize: 10,
  },
});
```

## Single app

#### Linking

Once we have all that configured, we can create links to our fonts for iOS and Android. If you have React Native ver. >= 0.69, you can use `npx react-native-asset`. For older versions, use `yarn react-native link`. Once that's done save everything and that's it!

#### Use

here's an example use of our typography system:

```ts
import { View, Text } from "react-native";
import { typographySystem, colors } from "@/styles";

export const Title: React.FC<{ content: string }> = ({ content }) => (
  <View>
    <Text style={{ ...typographySystem.H3Bold, color: colors.error.magneta01 }}>
      {content}
    </Text>
  </View>
);
```

## Monorepo

#### Building a shared folder

If you already have `typographySystem.ts` in your `styles` directory, you can then go to the root of the shared folder directory and edit the `index.ts` file there - adding the following at the end of that file:

```ts
export * from "./src/assets";
export * from "./src/styles/typographySystem";
```

Now, the `shared` directory should build correctly!

> To be 100% sure, remember to look at your `dist` folder after the `yarn` command.

#### Linking

Once we have everything else configured, we just have to create links to our fonts for iOS and Android. If you have React Native, ver. >= 0.69 you can use `npx react-native-asset`. For older versions, use `yarn react-native link`. Save everything and that's it! Just remember to do this for every app in your monorepo!

> If you are in the `shared` directory, the correct way to do that is using a script like this:

```bash
    cd ..
    cd app1
    npx react-native-asset (for RN >= 0.69) / yarn react-native-link (for RN < 0.69)
    cd ..
    cd app2
    ...
```

#### Use

If everything is correctly configured, you can now freely use your typography system in your applications.
Here's an example use of the typography system:

```ts
import { View, Text } from "react-native";
import { typographySystem, colors } from "@my-monorepo/shared";

export const Title: React.FC<{ content: string }> = ({ content }) => (
  <View>
    <Text style={{ ...typographySystem.H3Bold, color: colors.error.magneta01 }}>
      {content}
    </Text>
  </View>
);
```

> If you're having some trouble with a monorepo, try to remove your node_modules and Pods, and reinstall one more time.

## Correct direction structure

### Single app

```
  my-app/
    src/
        assets/
         index.ts
            fonts/
                index.ts
                fontFile.ttf
        styles/
            typographySystem.ts
            index.ts
    App.tsx
    react-native.config.js
```

**Monorepo**

```
  my-monorepo/
    packages/
        app1/
            App.tsx
            react-native.config.js
        app2/
            App.tsx
            react-native.config.js
        shared/
            dist/ (created after building this package)
            src/
                assets/
                    index.ts
                    fonts/
                        index.ts
                        fontFile.ttf
                styles/
                    typographySystem.ts
            index.ts
```

## Conclusion

Creating a typography system, in addition to the aforementioned code reduction, speeds up the application development process (especially if combined with a styling system and color palette!). If you have any questions, go ahead and let me know. If you do not know how a monorepo works for React Native applications, go ahead and read an [article about that here.](https://blog.graphqleditor.com/react-native-monorepo-with-shared-components)

## Enjoy!
