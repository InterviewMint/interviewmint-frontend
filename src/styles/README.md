# Styles

This directory contains global styles, themes, and CSS utilities.

## Structure

- **global.css** - Global styles and CSS resets
- **variables.css** - CSS custom properties (variables)
- **theme.ts** - Theme configuration (colors, typography, spacing)

## Example

```css
/* styles/variables.css */
:root {
  /* Colors */
  --color-primary: #3b82f6;
  --color-secondary: #8b5cf6;
  --color-success: #10b981;
  --color-error: #ef4444;
  --color-warning: #f59e0b;
  
  /* Typography */
  --font-family-base: 'Inter', system-ui, sans-serif;
  --font-size-sm: 0.875rem;
  --font-size-base: 1rem;
  --font-size-lg: 1.125rem;
  --font-size-xl: 1.25rem;
  
  /* Spacing */
  --spacing-xs: 0.25rem;
  --spacing-sm: 0.5rem;
  --spacing-md: 1rem;
  --spacing-lg: 1.5rem;
  --spacing-xl: 2rem;
  
  /* Border radius */
  --radius-sm: 0.25rem;
  --radius-md: 0.375rem;
  --radius-lg: 0.5rem;
}

/* styles/global.css */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: var(--font-family-base);
  font-size: var(--font-size-base);
  line-height: 1.5;
  color: var(--color-text);
  background-color: var(--color-background);
}
```

```tsx
// styles/theme.ts
export const theme = {
  colors: {
    primary: '#3b82f6',
    secondary: '#8b5cf6',
    success: '#10b981',
    error: '#ef4444',
    warning: '#f59e0b',
  },
  spacing: {
    xs: '0.25rem',
    sm: '0.5rem',
    md: '1rem',
    lg: '1.5rem',
    xl: '2rem',
  },
} as const;
```

## Best Practices

- Use CSS custom properties for theming
- Keep global styles minimal
- Consider using CSS modules or styled-components for component styles
- Maintain consistent design tokens
