# Utils

This directory contains utility functions and helper modules.

## Structure

Organize utilities by category or functionality.

## Naming Convention

- Use camelCase for utility file names (e.g., `formatters.ts`, `validators.ts`)
- Use descriptive function names

## Example

```tsx
// utils/formatters.ts
export const formatDate = (date: Date): string => {
  return new Intl.DateTimeFormat('en-US', {
    year: 'numeric',
    month: 'long',
    day: 'numeric',
  }).format(date);
};

export const formatCurrency = (amount: number, currency = 'USD'): string => {
  return new Intl.NumberFormat('en-US', {
    style: 'currency',
    currency,
  }).format(amount);
};

// utils/validators.ts
export const isValidEmail = (email: string): boolean => {
  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return emailRegex.test(email);
};

export const isValidUrl = (url: string): boolean => {
  try {
    new URL(url);
    return true;
  } catch {
    return false;
  }
};

// utils/string.ts
export const truncate = (str: string, length: number): string => {
  return str.length > length ? str.slice(0, length) + '...' : str;
};

export const capitalize = (str: string): string => {
  return str.charAt(0).toUpperCase() + str.slice(1).toLowerCase();
};
```

## Best Practices

- Keep functions pure when possible
- Write comprehensive unit tests for utilities
- Document complex utility functions with JSDoc
- Consider using libraries like lodash for common operations
