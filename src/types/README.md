# Types

This directory contains shared TypeScript type definitions and interfaces.

## Structure

Organize types by domain or feature.

## Naming Convention

- Use PascalCase for type and interface names
- Use descriptive names that indicate the purpose
- Consider using `.d.ts` files for declaration files

## Example

```tsx
// types/user.ts
export interface User {
  id: string;
  email: string;
  name: string;
  role: UserRole;
  createdAt: Date;
  updatedAt: Date;
}

export enum UserRole {
  ADMIN = 'admin',
  USER = 'user',
  GUEST = 'guest',
}

export type UserStatus = 'active' | 'inactive' | 'suspended';

// types/api.ts
export interface ApiResponse<T> {
  data: T;
  message: string;
  status: number;
}

export interface PaginatedResponse<T> extends ApiResponse<T[]> {
  total: number;
  page: number;
  pageSize: number;
}
```

## Best Practices

- Keep types close to where they're used when they're feature-specific
- Use this directory for shared types used across multiple features
- Consider using Zod schemas for runtime validation
- Export types as named exports
