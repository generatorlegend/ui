---
title: Accessibility Guidelines
description: Ensuring accessibility when using the component library
---

# Accessibility Guidelines

Accessibility is a crucial aspect of web development that ensures all users, including those with disabilities, can effectively use and navigate your application. This guide provides best practices for implementing accessibility features when using our component library.

## Table of Contents

1. [ARIA Attributes](#aria-attributes)
2. [Keyboard Navigation](#keyboard-navigation)
3. [Color Contrast](#color-contrast)
4. [Screen Reader Compatibility](#screen-reader-compatibility)
5. [Responsive Design](#responsive-design)

## ARIA Attributes

ARIA (Accessible Rich Internet Applications) attributes provide additional information to assistive technologies, enhancing the accessibility of your components.

### Key ARIA Attributes

- `aria-label`: Provides a label for elements that don't have visible text.
- `aria-labelledby`: References another element that serves as a label.
- `aria-describedby`: References another element that provides additional description.
- `aria-hidden`: Hides elements from assistive technologies when set to "true".

Example usage in our component library:

```jsx
<Button
  aria-label="Close modal"
  onClick={closeModal}
>
  <Icons.close className="h-4 w-4" />
</Button>
```

## Keyboard Navigation

Ensure that all interactive elements are accessible via keyboard navigation.

### Best Practices

1. Use native HTML elements when possible (e.g., `<button>`, `<a>`) as they have built-in keyboard accessibility.
2. Implement custom keyboard handlers for complex components.
3. Maintain a logical tab order.

Example of keyboard navigation in our `MainNav` component:

```jsx
<Link
  href="/docs/installation"
  className={cn(
    "transition-colors hover:text-foreground/80",
    pathname === "/docs/installation"
      ? "text-foreground"
      : "text-foreground/80"
  )}
>
  Docs
</Link>
```

The `Link` component ensures proper keyboard navigation between different sections of the documentation.

## Color Contrast

Maintain sufficient color contrast between text and background to ensure readability for all users, including those with visual impairments.

### Guidelines

- Aim for a contrast ratio of at least 4.5:1 for normal text and 3:1 for large text.
- Use tools like WebAIM's Contrast Checker to verify your color combinations.

In our component library, we use CSS variables for colors, making it easier to adjust and maintain proper contrast:

```css
:root {
  --background: 0 0% 100%;
  --foreground: 222.2 84% 4.9%;
}
```

## Screen Reader Compatibility

Ensure that your components work well with screen readers by providing meaningful text alternatives and proper semantic structure.

### Tips

1. Use semantic HTML elements (`<nav>`, `<main>`, `<header>`, etc.).
2. Provide alternative text for images and icons.
3. Use ARIA roles and attributes when necessary.

Example from our `SiteHeader` component:

```jsx
<Link
  href={siteConfig.links.github}
  target="_blank"
  rel="noreferrer"
>
  <Icons.gitHub className="h-4 w-4" />
  <span className="sr-only">GitHub</span>
</Link>
```

The `sr-only` class visually hides the text "GitHub" but keeps it accessible to screen readers.

## Responsive Design

Ensure that your components are usable across different devices and screen sizes.

### Best Practices

1. Use responsive units (e.g., rem, em, %) instead of fixed pixel values.
2. Implement a mobile-first approach.
3. Test your components on various devices and screen sizes.

Our component library uses Tailwind CSS classes for responsive design:

```jsx
<div className="mr-4 hidden md:flex">
  {/* Content visible on medium screens and larger */}
</div>
```

By following these accessibility guidelines, you can create more inclusive and user-friendly applications using our component library. Remember to test your implementation thoroughly with various assistive technologies and real users to ensure the best possible experience for all.