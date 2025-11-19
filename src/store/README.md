# Store

This directory contains Zustand state management stores.

## Structure

Each store should be in its own file and handle a specific domain of state.

## Naming Convention

- Use camelCase with Store suffix (e.g., `authStore.ts`, `userStore.ts`)
- Keep stores focused on a single domain

## Example

```tsx
// store/authStore.ts
import { create } from 'zustand';

interface User {
  id: string;
  email: string;
  name: string;
}

interface AuthState {
  user: User | null;
  token: string | null;
  isAuthenticated: boolean;
  login: (user: User, token: string) => void;
  logout: () => void;
}

export const useAuthStore = create<AuthState>((set) => ({
  user: null,
  token: null,
  isAuthenticated: false,

  login: (user, token) => {
    localStorage.setItem('token', token);
    set({ user, token, isAuthenticated: true });
  },

  logout: () => {
    localStorage.removeItem('token');
    set({ user: null, token: null, isAuthenticated: false });
  },
}));
```

## Best Practices

- Use Zustand's middleware for persistence and devtools
- Keep actions simple and delegate complex logic to services
- Use TypeScript for type-safe state management
- Consider using slices for large stores
