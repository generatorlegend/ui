---
title: Customization Guide
description: Learn how to customize the appearance and behavior of components using theming, CSS variables, and Tailwind CSS.
---

# Customization Guide

This guide will help you customize the appearance and behavior of components in your project. We'll cover theming, CSS variables, and how to extend or override default styles using Tailwind CSS.

## Table of Contents

1. [Theming](#theming)
2. [CSS Variables](#css-variables)
3. [Extending Tailwind CSS](#extending-tailwind-css)
4. [Overriding Default Styles](#overriding-default-styles)

## Theming

Our theming system is based on CSS variables, which allow for easy customization of colors, typography, and other design tokens. The theme is defined in the `:root` selector in the `globals.css` file.

### Light and Dark Themes

We provide both light and dark themes out of the box. The dark theme is applied using the `.dark` class. Here's an example of how the variables are defined:

```css
:root {
  --background: 0 0% 100%;
  --foreground: 240 10% 3.9%;
  /* ... other variables ... */
}

.dark {
  --background: 240 10% 3.9%;
  --foreground: 0 0% 98%;
  /* ... other variables ... */
}
```

To customize these themes, you can modify the values in the `globals.css` file.

## CSS Variables

Our design system uses CSS variables to define colors, spacing, and other design tokens. Here are some key variables you can customize:

- `--background`: Background color
- `--foreground`: Text color
- `--primary`: Primary color for buttons and interactive elements
- `--secondary`: Secondary color for less prominent elements
- `--accent`: Accent color for highlights
- `--radius`: Border radius for rounded corners

To use these variables in your custom styles, you can reference them like this:

```css
.custom-element {
  background-color: hsl(var(--background));
  color: hsl(var(--foreground));
}
```

## Extending Tailwind CSS

Our project uses Tailwind CSS for utility classes. You can extend the default Tailwind configuration by modifying the `tailwind.config.cjs` file.

To add custom colors, fonts, or other design tokens, update the `theme` section of the configuration:

```javascript
module.exports = {
  // ...
  theme: {
    extend: {
      colors: {
        custom: {
          light: '#f3f4f6',
          dark: '#1f2937',
        },
      },
      fontFamily: {
        custom: ['CustomFont', 'sans-serif'],
      },
    },
  },
  // ...
}
```

After extending the configuration, you can use your custom classes in your components:

```jsx
<div className="bg-custom-light dark:bg-custom-dark font-custom">
  Custom styled content
</div>
```

## Overriding Default Styles

To override default styles, you can use Tailwind's `@apply` directive in your CSS or create custom utility classes.

1. Using `@apply` in your CSS:

```css
.btn-primary {
  @apply bg-blue-500 text-white font-bold py-2 px-4 rounded;
}

.btn-primary:hover {
  @apply bg-blue-700;
}
```

2. Creating custom utility classes in `tailwind.config.cjs`:

```javascript
module.exports = {
  // ...
  theme: {
    extend: {
      // ...
    },
  },
  plugins: [
    function ({ addUtilities }) {
      const newUtilities = {
        '.custom-underline': {
          textDecoration: 'underline',
          textDecorationColor: 'currentColor',
          textDecorationThickness: '2px',
          textUnderlineOffset: '4px',
        },
      }
      addUtilities(newUtilities)
    },
  ],
}
```

Then use your custom utility class in your components:

```jsx
<a href="#" className="custom-underline">
  Custom underlined link
</a>
```

By following this guide, you should be able to effectively customize the appearance and behavior of components in your project using theming, CSS variables, and Tailwind CSS extensions.