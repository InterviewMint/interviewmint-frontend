# Features

This directory contains feature-specific modules organized by domain.

## Structure

Each feature should be self-contained with its own components, hooks, services, and types.

```
features/
  auth/
    components/
    hooks/
    services/
    types/
    index.ts
  interviews/
    components/
    hooks/
    services/
    types/
    index.ts
```

## Naming Convention

- Use lowercase for feature folder names (e.g., `auth`, `interviews`, `profile`)
- Each feature exports its public API through an index file

## Example

```tsx
// features/auth/hooks/useAuth.ts
export const useAuth = () => {
  // Authentication logic
};

// features/auth/index.ts
export { useAuth } from './hooks/useAuth';
export type { User } from './types';
```

## Best Practices

- Keep features independent and loosely coupled
- Share common logic through hooks and services
- Use feature flags for experimental features
