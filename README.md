# Yass - The fabulous atomic CSS library 

Yass Builds on concepts from [Hucssley](), [TurretCSS](), and [Rainbow](https://github.com/scottdejonge/rainbow) and consolidates them in a single package.

## Quickstart

### React
```bash
$ npm i yass
```

```js
import 'yass'

export default function MyComponent() {
  return (
    <div className={`
      border:red-500 
      width:500
      height:500
    `}>
    </div>
  )
}
```

### Vue
```bash
$ npm i yass
```

```Vue
<script>
import 'yass'

export default {

}
</script>

<template>
  <div v-bind:class="`
    border:red-500 
    width:500
    height:500
  `">
  </div>
</template>
```

Yep, it's that simple.

## Core Concepts
### No Steep Learning Curve

Although there are some other great atomic CSS libraries out there like [TailwindCSS](), it can be annoying when you're first learning them to constantly look up documentation to find class names. Yass takes inspiration from Hucssley by using class names that are as close as possible to the original CSS properties. 

Most of the time, the class you need will have exactly the same name as the relevant style. For example:
```html
<!-- Vanilla HTML and CSS -->
<div style="display:flex;">
  ...
</div>

<!-- Yass -->
<div class="display:flex">
  ...
</div>
```

As a result, if you know how to write CSS, then you know how to write simple Yass. There are two cases when Yass is different to CSS
1. When leveraging the design system. This will happen whenever you write Yass related to:

  - border-radius
  - border-width
  - box-shadow
  - colors
  - size
  - spacing
  - typography

However, even in these cases, Yass behaves in a predictable way. For example:
```html
<div class="background-color:blue-200">
  <p class="color:neutral-900">Some dark gray text on a light blue background.</p>
</div>
```
Here the CSS color codes have been replaced with color codes from the Rainbow color library. See the 'Colors' section for a complete reference of available colors.

2. Using a utility class.

These classes don't exist in vanilla CSS, and are provided to add more powerful functionality to Yass. for example `margin-vertical:200`. For a full list of utility classes, see the 'Utility Classes' section.


### Baked In Accessibility


## Design Tokens

### Border Radius
### Border Width
### Box Shadow

### Colors

Yass uses [Rainbow](https://github.com/scottdejonge/rainbow) colors internally because they allow for enough saturation for contrast whilst not being too overwhelming, which assists in creating accessible websites. The available colors are:

|  |neutral|red|orange|yellow|green|teal|blue|purple|pink|
|---|---|---|---|---|---|---|---|---|---|
|50|hsl(220, 25%, 97.5%)|hsl(0, 100%, 97.5%)|hsl(25, 100%, 97.5%)|hsl(50, 100%, 97.5%)|hsl(135, 80%, 97.5%)|hsl(180, 80%, 97.5%)|hsl(220, 80%, 97.5%)|hsl(280, 80%, 97.5%)|hsl(320, 80%, 97.5%)|
|100|hsl(220, 25%, 95%)|hsl(0, 100%, 95%)|hsl(25, 100%, 95%)|hsl(50, 100%, 95%)|hsl(135, 80%, 95%)|hsl(180, 80%, 95%)|hsl(220, 80%, 95%)|hsl(280, 80%, 95%)|hsl(320, 80%, 95%)|
|200|hsl(220, 25%, 85%)|hsl(0, 100%, 85%)|hsl(25, 100%, 85%)|hsl(50, 100%, 85%)|hsl(135, 80%, 85%)|hsl(180, 80%, 85%)|hsl(220, 80%, 85%)|hsl(280, 80%, 85%)|hsl(320, 80%, 85%)|
|300|hsl(220, 25%, 75%)|hsl(0, 100%, 75%)|hsl(25, 100%, 75%)|hsl(50, 100%, 75%)|hsl(135, 80%, 75%)|hsl(180, 80%, 75%)|hsl(220, 80%, 75%)|hsl(280, 80%, 75%)|hsl(320, 80%, 75%)|
|400|hsl(220, 25%, 65%)|hsl(0, 100%, 65%)|hsl(25, 100%, 60%)|hsl(50, 100%, 60%)|hsl(135, 80%, 45%)|hsl(180, 80%, 45%)|hsl(220, 80%, 65%)|hsl(280, 80%, 65%)|hsl(320, 80%, 65%)|
|500|hsl(220, 25%, 50%)|hsl(0, 100%, 35%)|hsl(25, 100%, 50%)|hsl(50, 100%, 50%)|hsl(135, 80%, 35%)|hsl(180, 80%, 35%)|hsl(220, 80%, 50%)|hsl(280, 80%, 50%)|hsl(320, 80%, 50%)|
|600|hsl(220, 25%, 40%)|hsl(0, 100%, 30%)|hsl(25, 100%, 40%)|hsl(50, 100%, 40%)|hsl(135, 80%, 30%)|hsl(180, 80%, 30%)|hsl(220, 80%, 40%)|hsl(280, 80%, 40%)|hsl(320, 80%, 40%)|
|700|hsl(220, 25%, 30%)|hsl(0, 100%, 25%)|hsl(25, 100%, 35%)|hsl(50, 100%, 35%)|hsl(135, 80%, 25%)|hsl(180, 80%, 25%)|hsl(220, 80%, 35%)|hsl(280, 80%, 35%)|hsl(320, 80%, 35%)|
|800|hsl(220, 25%, 20%)|hsl(0, 100%, 20%)|hsl(25, 100%, 25%)|hsl(50, 100%, 25%)|hsl(135, 80%, 20%)|hsl(180, 80%, 20%)|hsl(220, 80%, 30%)|hsl(280, 80%, 30%)|hsl(320, 80%, 30%)|
|900|hsl(220, 25%, 15%)|hsl(0, 100%, 15%)|hsl(25, 100%, 20%)|hsl(50, 100%, 20%)|hsl(135, 80%, 15%)|hsl(180, 80%, 15%)|hsl(220, 80%, 20%)|hsl(280, 80%, 20%)|hsl(320, 80%, 20%)|

### Size
### Spacing
### Typography

### Utility Classes

To make life easier, Yass ships with some utility classes that allow for 

## Gotchas 

### Semi-colons
When copy/pasting styles, or maybe just due to muscle memory, you might accidentally include a semi-colon in the class name:
```html
<div class="border-width:100;">
  ...
</div>
<!-- OR -->
<div class="
  display:flex;
  justify-content:center;
">
  ...
</div>
```
This will not work, since Yass won't be able to determine that when you wrote `display:flex;` you actually meant `display:flex`.

### use `class` instead of `style`

Although it looks like you're writing CSS, `border-width:100` is not a valid CSS rule, so:
```html
<div style="border-width:100">
  ...
</div>
```
won't work. All Yass rules need to go in `class`. 

### Multi valued CSS properties 

You might run into a situation where you want to uniqule style different sides of an element. For example, in vanilla CSS, it might look like this:

```html
<div style="
  margin: 4px 0px 4px 4px;
">
  ...
</div>
```

At first glance it might be confusing how to convert this to Yass, since `margin:200 0 200 200` is not a valid class name because it contains spaces. However, whenenver a CSS property allows for multiple values, that property is actually a shorthand for multiple other CSS properties. So, the correct Yass code is actually:
```html
<div style="
  margin-top:200
  margin-right:0
  margin-bottom:200
  margin-left:200
">
  ...
</div>
```
It's a little verbose, but Yass provides utility classes to help, and since `div`s have no margin by default, it can be cleaned up to look like this:
```html
<div style="
  margin-vertical:200
  margin-left:200
">
  ...
</div>
```

## Best Practises

For simplicity, the examples in this readme have written Yass inline in the HTML, however, this is not recommended for any code that is intended to scale. The implementation details for best practise will change depending on your stack, but it is generally recommended to pull your Yass styles out to a separate file and import them. For example:

`styles.js`
```js
export default {
  root: `
    border-radius:300
    border-width:300
    border-style:solid
  `,
  variants: {
    primary: `
      background-color:blue-500
      border-color:blue-500
      color:neutral-50
    `,
    neutral: `
      background-color:neutral-50
      border-color:neutral-50
      color:neutral-900
    `,
  },
}
```

Using these styles in a React project, might look something like this:

`YassButton.jsx`
```js
import styles from './styles.js'
import 'yass'

export function YassButton({ variant, children }) {
  return (
    <button
      className={[
        styles.root,
        styles.variants[variant],
      ].join(' ')}
    >
      { children }
    </button>
  )
}
```

Using these styles in a Vue project, might look something like this:

`YassButton.vue`
```vue
<script>
import styles from './styles.js'
import 'yass'

export default {
  name: 'YassButton',
  props: {
    variant: {
      default: 'primary',
      type: String,
    }
  },
}
</script>

<template>
 <button
    v-bind:class="[
      styles.root,
      styles.variants[variant],
    ]"
  >
    <slot></slot>
  </button>
</template>
```
