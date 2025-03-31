# Component Catalog

This catalog provides an overview of all available components in our library, organized by category. Each component includes a brief description, its props, and example usage to help you quickly find and implement the right components for your project.

## Table of Contents

1. [Layout Components](#layout-components)
2. [Form Components](#form-components)
3. [Data Display Components](#data-display-components)
4. [Navigation Components](#navigation-components)
5. [Feedback Components](#feedback-components)

## Layout Components

### Container

A basic layout component that centers content and provides consistent padding.

**Props:**
- `maxWidth`: string (optional) - Sets the maximum width of the container. Default: '1200px'
- `padding`: string (optional) - Sets the padding of the container. Default: '1rem'

**Example Usage:**
```jsx
import { Container } from '@/components/layout/Container';

function MyPage() {
  return (
    <Container maxWidth="800px">
      <h1>Welcome to my page</h1>
      <p>This content is centered and has a max width of 800px.</p>
    </Container>
  );
}
```

### Grid

A flexible grid system for creating responsive layouts.

**Props:**
- `columns`: number (optional) - Sets the number of columns. Default: 12
- `gap`: string (optional) - Sets the gap between grid items. Default: '1rem'

**Example Usage:**
```jsx
import { Grid } from '@/components/layout/Grid';

function MyGrid() {
  return (
    <Grid columns={3} gap="2rem">
      <div>Column 1</div>
      <div>Column 2</div>
      <div>Column 3</div>
    </Grid>
  );
}
```

## Form Components

### Input

A customizable input component for text entry.

**Props:**
- `type`: string - Sets the input type (e.g., 'text', 'email', 'password')
- `placeholder`: string (optional) - Sets the input placeholder text
- `value`: string - The current value of the input
- `onChange`: function - Callback function when the input value changes

**Example Usage:**
```jsx
import { Input } from '@/components/form/Input';

function MyForm() {
  const [name, setName] = useState('');

  return (
    <Input
      type="text"
      placeholder="Enter your name"
      value={name}
      onChange={(e) => setName(e.target.value)}
    />
  );
}
```

### Button

A versatile button component with multiple styles and sizes.

**Props:**
- `variant`: string (optional) - Sets the button style ('primary', 'secondary', 'outline'). Default: 'primary'
- `size`: string (optional) - Sets the button size ('small', 'medium', 'large'). Default: 'medium'
- `onClick`: function - Callback function when the button is clicked

**Example Usage:**
```jsx
import { Button } from '@/components/form/Button';

function MyComponent() {
  return (
    <Button variant="secondary" size="large" onClick={() => console.log('Button clicked')}>
      Click me
    </Button>
  );
}
```

## Data Display Components

### Table

A responsive table component for displaying structured data.

**Props:**
- `data`: array - An array of objects representing the table data
- `columns`: array - An array of column definitions (e.g., [{header: 'Name', accessor: 'name'}])

**Example Usage:**
```jsx
import { Table } from '@/components/data/Table';

function MyTable() {
  const data = [
    { id: 1, name: 'John Doe', age: 30 },
    { id: 2, name: 'Jane Smith', age: 25 },
  ];

  const columns = [
    { header: 'ID', accessor: 'id' },
    { header: 'Name', accessor: 'name' },
    { header: 'Age', accessor: 'age' },
  ];

  return <Table data={data} columns={columns} />;
}
```

### Card

A versatile card component for displaying content in a boxed layout.

**Props:**
- `title`: string (optional) - Sets the card title
- `image`: string (optional) - URL of the card's header image
- `footer`: ReactNode (optional) - Content to be displayed in the card footer

**Example Usage:**
```jsx
import { Card } from '@/components/data/Card';

function MyCard() {
  return (
    <Card
      title="Featured Product"
      image="/images/product.jpg"
      footer={<Button>Buy Now</Button>}
    >
      <p>This is an amazing product that you'll love!</p>
    </Card>
  );
}
```

## Navigation Components

### Navbar

A responsive navigation bar component.

**Props:**
- `logo`: ReactNode - The logo or brand element
- `links`: array - An array of navigation link objects (e.g., [{label: 'Home', href: '/'}])

**Example Usage:**
```jsx
import { Navbar } from '@/components/navigation/Navbar';

function MyNavbar() {
  const links = [
    { label: 'Home', href: '/' },
    { label: 'About', href: '/about' },
    { label: 'Contact', href: '/contact' },
  ];

  return <Navbar logo={<img src="/logo.svg" alt="Logo" />} links={links} />;
}
```

### Pagination

A component for navigating through multiple pages of content.

**Props:**
- `currentPage`: number - The current active page
- `totalPages`: number - The total number of pages
- `onPageChange`: function - Callback function when a page is selected

**Example Usage:**
```jsx
import { Pagination } from '@/components/navigation/Pagination';

function MyPagination() {
  const [currentPage, setCurrentPage] = useState(1);
  const totalPages = 10;

  return (
    <Pagination
      currentPage={currentPage}
      totalPages={totalPages}
      onPageChange={(page) => setCurrentPage(page)}
    />
  );
}
```

## Feedback Components

### Toast

A component for displaying brief notifications or messages.

**Props:**
- `message`: string - The message to be displayed
- `type`: string (optional) - The type of toast ('success', 'error', 'warning', 'info'). Default: 'info'
- `duration`: number (optional) - The duration in milliseconds to show the toast. Default: 3000

**Example Usage:**
```jsx
import { Toast } from '@/components/feedback/Toast';

function MyComponent() {
  const [showToast, setShowToast] = useState(false);

  return (
    <>
      <Button onClick={() => setShowToast(true)}>Show Toast</Button>
      {showToast && (
        <Toast
          message="Operation successful!"
          type="success"
          duration={5000}
        />
      )}
    </>
  );
}
```

### Modal

A customizable modal component for displaying content in an overlay.

**Props:**
- `isOpen`: boolean - Determines if the modal is visible
- `onClose`: function - Callback function when the modal is closed
- `title`: string (optional) - Sets the modal title

**Example Usage:**
```jsx
import { Modal } from '@/components/feedback/Modal';

function MyModal() {
  const [isOpen, setIsOpen] = useState(false);

  return (
    <>
      <Button onClick={() => setIsOpen(true)}>Open Modal</Button>
      <Modal isOpen={isOpen} onClose={() => setIsOpen(false)} title="My Modal">
        <p>This is the modal content.</p>
      </Modal>
    </>
  );
}
```

This catalog provides an overview of the main components available in our library. For more detailed information on each component, including all available props and advanced usage examples, please refer to the individual component documentation.