# Services

This directory contains API services and external integrations.

## Structure

- **api/** - API client configuration and services
- **storage/** - Local storage, session storage utilities
- **analytics/** - Analytics and tracking services

## Naming Convention

- Use descriptive names with Service suffix (e.g., `authService.ts`, `userService.ts`)
- Group related services in subdirectories

## Example

```tsx
// services/api/authService.ts
import axios from 'axios';
import { API_BASE_URL } from '@/constants';

export const authService = {
  login: async (email: string, password: string) => {
    const response = await axios.post(`${API_BASE_URL}/auth/login`, {
      email,
      password,
    });
    return response.data;
  },

  logout: async () => {
    const response = await axios.post(`${API_BASE_URL}/auth/logout`);
    return response.data;
  },

  getCurrentUser: async () => {
    const response = await axios.get(`${API_BASE_URL}/auth/me`);
    return response.data;
  },
};
```

## Best Practices

- Use axios interceptors for common logic (auth headers, error handling)
- Implement proper error handling and retry logic
- Use TypeScript for type-safe API calls
- Consider using React Query for data fetching
