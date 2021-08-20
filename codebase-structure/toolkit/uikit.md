# BBT-Swap/UIkit

## BBT-Swap/UIkit

> View repository on [Github](https://github.com/thanakiat-gusgus/bbt-uikit.git)

## Install bbt-swap/uikit

```text
yarn add @bbt-swap/uikit
```

## Setup

### Theme

Before using Pancake UIkit, you need to provide the theme file to styled-component.

```text
import { ThemeProvider } from 'styled-components'
import { light, dark } from '@bbt-swap/uikit'
...
<ThemeProvider theme={isDark}>...</ThemeProvider>
```

### Reset

A reset CSS is available as a global styled component.

```text
import { ResetCSS } from '@bbt-swap/uikit'
...
<ResetCSS />
```

### Types

This project is built with Typescript and export all the relevant types.

## How to use the BBT-swap/UIkit

If you want to use components from the UIkit, check the [Storybook documentation](http://207.148.72.50:6006)

