# Hooks

This directory contains custom React hooks that can be reused across the application.

## Naming Convention

- All hooks must start with `use` (e.g., `useAuth.ts`, `useDebounce.ts`)
- Use descriptive names that indicate the hook's purpose

## Example

```tsx
// hooks/useDebounce.ts
import { useEffect, useState } from 'react';

export const useDebounce = <T,>(value: T, delay: number): T => {
  const [debouncedValue, setDebouncedValue] = useState<T>(value);

  useEffect(() => {
    const handler = setTimeout(() => {
      setDebouncedValue(value);
    }, delay);

    return () => {
      clearTimeout(handler);
    };
  }, [value, delay]);

  return debouncedValue;
};
```

## Best Practices

- Keep hooks focused on a single responsibility
- Document complex hooks with JSDoc comments
- Export hooks with named exports for better tree-shaking
- Test hooks using React Testing Library
