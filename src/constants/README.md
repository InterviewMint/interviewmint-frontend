# Constants

This directory contains application-wide constants and configuration values.

## Structure

Organize constants by domain or purpose.

## Naming Convention

- Use UPPER_SNAKE_CASE for constant names
- Group related constants in objects or enums

## Example

```tsx
// constants/api.ts
export const API_BASE_URL = import.meta.env.VITE_API_BASE_URL || 'http://localhost:3000/api';
export const API_TIMEOUT = 30000; // 30 seconds

export const API_ENDPOINTS = {
  AUTH: {
    LOGIN: '/auth/login',
    LOGOUT: '/auth/logout',
    REGISTER: '/auth/register',
    REFRESH: '/auth/refresh',
  },
  USERS: {
    LIST: '/users',
    DETAIL: (id: string) => `/users/${id}`,
    UPDATE: (id: string) => `/users/${id}`,
    DELETE: (id: string) => `/users/${id}`,
  },
} as const;

// constants/routes.ts
export const ROUTES = {
  HOME: '/',
  LOGIN: '/login',
  REGISTER: '/register',
  DASHBOARD: '/dashboard',
  PROFILE: '/profile',
  SETTINGS: '/settings',
} as const;

// constants/app.ts
export const APP_NAME = 'InterviewMint';
export const APP_VERSION = '1.0.0';
export const DEFAULT_PAGE_SIZE = 20;
export const MAX_FILE_SIZE = 5 * 1024 * 1024; // 5MB
```

## Best Practices

- Use environment variables for configuration that changes between environments
- Document the purpose of each constant
- Use `as const` for object constants to get literal types
- Keep magic numbers and strings as constants
