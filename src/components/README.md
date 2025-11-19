# Components

This directory contains reusable UI components organized by category.

## Structure

- **common/** - Shared components used across the application (e.g., Button, Input, Card)
- **ui/** - UI-specific components (e.g., Modal, Dropdown, Tooltip)
- **forms/** - Form-related components (e.g., FormInput, FormSelect, FormCheckbox)

## Naming Convention

- Use PascalCase for component names (e.g., `Button.tsx`, `UserCard.tsx`)
- Each component should have its own folder if it includes styles or tests
- Export components from index files for cleaner imports

## Example

```tsx
// components/common/Button/Button.tsx
export interface ButtonProps {
  label: string;
  onClick: () => void;
  variant?: 'primary' | 'secondary';
}

export const Button: React.FC<ButtonProps> = ({ label, onClick, variant = 'primary' }) => {
  return (
    <button className={`btn btn-${variant}`} onClick={onClick}>
      {label}
    </button>
  );
};
```
