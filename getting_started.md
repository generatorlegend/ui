# Getting Started with shadcn/ui

This guide will walk you through the process of setting up and using shadcn/ui, a beautifully-designed and accessible component library that works with your favorite frameworks.

## Installation

To get started with shadcn/ui, you'll need to initialize your project and install the necessary dependencies.

1. Open your terminal and navigate to your project directory.

2. Run the following command to initialize your project:

```bash
npx shadcn-ui@latest init
```

3. The CLI will prompt you with a series of questions to configure your project. Here's an example of the options you might encounter:

   - Would you like to use TypeScript? (Recommended)
   - Which style would you like to use? (Default: New York)
   - Which color would you like to use as the base color?
   - Where is your global CSS file?
   - Would you like to use CSS variables for theming?
   - Are you using a custom tailwind prefix?
   - Where is your tailwind.config.js located?
   - Configure the import alias for components
   - Configure the import alias for utils
   - Are you using React Server Components?

Answer these questions based on your project requirements.

4. After completing the initialization process, the CLI will create a `components.json` file in your project root, containing your configuration.

## Adding Components

To add components to your project, use the `add` command:

```bash
npx shadcn-ui@latest add [component-name]
```

For example, to add a button component:

```bash
npx shadcn-ui@latest add button
```

This command will add the necessary files for the button component to your project.

## Using Components

After adding components, you can import and use them in your project. Here's an example of how to use the Button component:

```jsx
import { Button } from "@/components/ui/button"

export default function MyComponent() {
  return (
    <Button variant="default">
      Click me
    </Button>
  )
}
```

## Customization

shadcn/ui components are built with Tailwind CSS, making them highly customizable. You can modify the appearance of components by editing the Tailwind classes or adjusting the `tailwind.config.js` file.

To customize the base styles, you can edit the CSS variables in your global CSS file (usually `app/globals.css` or similar).

## Examples

Here's a more complex example using multiple components:

```jsx
import { Card, CardHeader, CardTitle, CardDescription, CardContent, CardFooter } from "@/components/ui/card"
import { Button } from "@/components/ui/button"

export default function ExampleCard() {
  return (
    <Card>
      <CardHeader>
        <CardTitle>Card Title</CardTitle>
        <CardDescription>Card Description</CardDescription>
      </CardHeader>
      <CardContent>
        <p>Card Content</p>
      </CardContent>
      <CardFooter>
        <Button>Action</Button>
      </CardFooter>
    </Card>
  )
}
```

This example demonstrates how to compose a card component with various sub-components and include a button within it.

## Next Steps

- Explore the full range of available components in the documentation.
- Learn about advanced customization techniques.
- Check out the example projects for inspiration on how to structure your application.

Remember, shadcn/ui is designed to be flexible and adaptable to your needs. Feel free to modify and extend the components to fit your specific requirements.