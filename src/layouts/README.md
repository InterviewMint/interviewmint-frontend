# Layouts

This directory contains layout components that wrap pages and define the overall structure.

## Structure

Each layout defines a specific page structure (e.g., with/without sidebar, header, footer).

## Naming Convention

- Use PascalCase with Layout suffix (e.g., `MainLayout.tsx`, `AuthLayout.tsx`)

## Example

```tsx
// layouts/MainLayout.tsx
import { ReactNode } from 'react';

interface MainLayoutProps {
  children: ReactNode;
}

export const MainLayout: React.FC<MainLayoutProps> = ({ children }) => {
  return (
    <div className="main-layout">
      <header className="header">
        <nav>
          {/* Navigation */}
        </nav>
      </header>
      <main className="content">
        {children}
      </main>
      <footer className="footer">
        {/* Footer content */}
      </footer>
    </div>
  );
};

// layouts/AuthLayout.tsx
export const AuthLayout: React.FC<{ children: ReactNode }> = ({ children }) => {
  return (
    <div className="auth-layout">
      <div className="auth-container">
        {children}
      </div>
    </div>
  );
};
```

## Best Practices

- Keep layouts focused on structure, not business logic
- Use layouts with React Router for consistent page structure
- Make layouts responsive
- Consider creating layout variants for different viewports
