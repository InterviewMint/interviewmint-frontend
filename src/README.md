# Source Directory Structure

This document describes the organization of the InterviewMint frontend source code.

## Directory Overview

```
src/
├── assets/          # Static assets (images, fonts, etc.)
├── components/      # Reusable UI components
│   ├── common/      # Shared components (Button, Input, Card)
│   ├── ui/          # UI-specific components (Modal, Dropdown)
│   └── forms/       # Form components
├── pages/           # Page-level components
├── features/        # Feature-specific modules
├── hooks/           # Custom React hooks
├── services/        # API services and external integrations
│   ├── api/         # API client and services
│   ├── storage/     # Storage utilities
│   └── analytics/   # Analytics services
├── store/           # Zustand state management
├── types/           # TypeScript type definitions
├── utils/           # Utility functions and helpers
├── constants/       # Application constants
├── config/          # Configuration files
├── layouts/         # Layout components
└── styles/          # Global styles and theme

## Architecture Principles

### Component Organization

- **Components**: Reusable UI building blocks, organized by category
- **Pages**: Route-level components that compose features and components
- **Features**: Self-contained modules with their own components, hooks, and logic
- **Layouts**: Structural wrappers that define page templates

### State Management

- **Zustand** for global state management (auth, user preferences, etc.)
- **React Query** for server state (API data fetching and caching)
- **Local state** (useState) for component-specific state

### Code Organization Best Practices

1. **Colocation**: Keep related code close together
2. **Single Responsibility**: Each module should have one clear purpose
3. **Dependency Direction**: Dependencies should flow toward the domain layer
4. **Abstraction Levels**: Separate business logic from presentation

### Import Conventions

Use path aliases for cleaner imports:

```tsx
// Bad
import { Button } from '../../../components/common/Button';

// Good
import { Button } from '@/components/common';
```

Configure path aliases in `tsconfig.json`:

```json
{
  "compilerOptions": {
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}
```

## Technology Stack

- **React 19** - UI library
- **TypeScript** - Type safety
- **Vite** - Build tool and dev server
- **React Query** - Server state management
- **Zustand** - Client state management
- **Axios** - HTTP client
- **Zod** - Schema validation

## Getting Started

1. Explore each directory's README.md for specific guidelines
2. Follow existing patterns when adding new code
3. Write tests for critical functionality
4. Keep components small and focused
5. Document complex logic

## File Naming Conventions

- **Components**: PascalCase (e.g., `UserCard.tsx`)
- **Hooks**: camelCase with `use` prefix (e.g., `useAuth.ts`)
- **Utils**: camelCase (e.g., `formatters.ts`)
- **Types**: PascalCase (e.g., `User.ts`)
- **Constants**: UPPER_SNAKE_CASE or camelCase files (e.g., `API_ENDPOINTS`)

## Additional Resources

- [React Best Practices](https://react.dev/learn)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [Zustand Documentation](https://zustand-demo.pmnd.rs/)
- [React Query Documentation](https://tanstack.com/query/latest)
