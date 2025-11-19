# Pages

This directory contains page-level components that represent routes in the application.

## Structure

Each page should be in its own folder with related components and logic.

## Naming Convention

- Use PascalCase for page names (e.g., `HomePage.tsx`, `LoginPage.tsx`)
- Each page can have a folder containing the main page component and page-specific components

## Example

```tsx
// pages/Home/HomePage.tsx
export const HomePage: React.FC = () => {
  return (
    <div>
      <h1>Welcome to InterviewMint</h1>
    </div>
  );
};
```

## Best Practices

- Pages should be thin and delegate logic to hooks and services
- Keep page-specific components in the page folder
- Use feature modules for complex page logic
