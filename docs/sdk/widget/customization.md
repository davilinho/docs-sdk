---
id: customization
title: Customization
---

You can customize the look an feel of your widget integration through the `theme` option on the widget initialization.

```ts
// Typescript
type Theme = {
  position?: "left" | "right";
  launcher?: "base" | "extended";
  text?: { title: string; launcher: string };
  colors?: {
    primary: string;
    primaryContrast: string;
    secondary: string;
    accent: string;
    messageTextOutgoing: string;
    messageTextIncoming: string;
    bubbleBackgroundOutgoing: string;
    bubbleBackgroundIncoming: string;
    alertText: string;
    alertBackground: string;
  };
};
```

## Position

```ts
// Typescript
type Theme = {
  position?: "left" | "right";
};
```

Example:

```js
MediquoWidget.init({
  apiKey: <YOUR-API-KEY>,
  accessToken: <USER-ACCESS-TOKEN>,
  theme: {
    position: "left"
  },
```

## Launcher

```ts
// Typescript
type Theme = {
  launcher?: "base" | "extended";
};
```

Example:

```js
MediquoWidget.init({
  apiKey: <YOUR-API-KEY>,
  accessToken: <USER-ACCESS-TOKEN>,
  theme: {
    launcher: "extended"
  },
```

## Text

```ts
// Typescript
type Theme = {
  text?: { title: string; launcher: string };
};
```

Example:

```js
MediquoWidget.init({
  apiKey: <YOUR-API-KEY>,
  accessToken: <USER-ACCESS-TOKEN>,
  theme: {
    text: {
      title: "Custom title",
      launcher: "Custom launcher"
    }
  },
```

## Colors

```ts
// Typescript
type Theme = {
  colors?: {
    primary: string;
    primaryContrast: string;
    secondary: string;
    accent: string;
    messageTextOutgoing: string;
    messageTextIncoming: string;
    bubbleBackgroundOutgoing: string;
    bubbleBackgroundIncoming: string;
    alertText: string;
    alertBackground: string;
  };
};
```

Example:

```js
MediquoWidget.init({
  apiKey: <YOUR-API-KEY>,
  accessToken: <USER-ACCESS-TOKEN>,
  theme: {
    colors: {
      primary: "#1C93DE",
      primaryContrast: "#FFFFFF",
      secondary: "#3C50EC",
      accent: "#42CECE",
      messageTextOutgoing: "#201552",
      messageTextIncoming: "#201552",
      bubbleBackgroundOutgoing: "#ECEFF1",
      bubbleBackgroundIncoming: "#F4FAFD",
      alertText: "#201552",
      alertBackground: "#F4FAFD",
    },
  },
```