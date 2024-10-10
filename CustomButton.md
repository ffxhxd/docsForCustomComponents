# CustomButton Component Documentation

## Overview

The `CustomButton` component is a flexible and customizable button built on top of Material-UI's Button component. It offers additional customization options while maintaining compatibility with MUI's theming system.

## Import

```typescript
import CustomButton from './path/to/CustomButton';
```

## Props

The `CustomButton` component accepts all props from MUI's Button component, plus the following custom props:

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `size` | `'small' \| 'medium' \| 'large'` | `'medium'` | Sets the size of the button. |
| `variant` | `'text' \| 'outlined' \| 'contained'` | `'contained'` | Sets the variant of the button. |
| `color` | `'primary' \| 'secondary' \| 'error' \| 'info' \| 'success' \| 'warning' \| string` | `'primary'` | Sets the color of the button. Can be a theme color or a custom color string. |
| `fontSize` | `number \| string` | - | Custom font size for the button text. |
| `fullWidth` | `boolean` | `false` | If `true`, the button will take up the full width of its container. |
| `rounded` | `boolean` | `false` | If `true`, the button will have fully rounded corners (pill shape). |
| `elevation` | `number` | - | Custom elevation (shadow) for the button. |
| `uppercase` | `boolean` | `false` | If `true`, the button text will be in uppercase. |
| `primaryColor` | `string` | - | Overrides the primary color for this specific button instance. |
| `secondaryColor` | `string` | - | Overrides the secondary color for this specific button instance. |

## Usage Examples

### Basic Usage

```jsx
<CustomButton>Click me</CustomButton>
```

### Different Sizes

```jsx
<CustomButton size="small">Small</CustomButton>
<CustomButton size="medium">Medium</CustomButton>
<CustomButton size="large">Large</CustomButton>
```

### Variants

```jsx
<CustomButton variant="text">Text</CustomButton>
<CustomButton variant="outlined">Outlined</CustomButton>
<CustomButton variant="contained">Contained</CustomButton>
```

### Colors

```jsx
<CustomButton color="primary">Primary</CustomButton>
<CustomButton color="secondary">Secondary</CustomButton>
<CustomButton color="error">Error</CustomButton>
<CustomButton color="info">Info</CustomButton>
<CustomButton color="success">Success</CustomButton>
<CustomButton color="warning">Warning</CustomButton>
```

### Custom Styling

```jsx
<CustomButton 
  rounded 
  uppercase 
  fontSize="1.2rem" 
  elevation={3}
>
  Custom Style
</CustomButton>
```

### Full Width Button

```jsx
<CustomButton fullWidth>Full Width Button</CustomButton>
```

### Custom Colors

```jsx
<CustomButton primaryColor="#8E24AA">Custom Primary</CustomButton>
<CustomButton secondaryColor="#00BCD4">Custom Secondary</CustomButton>
```

### With Icon

```jsx
import SendIcon from '@mui/icons-material/Send';

<CustomButton endIcon={<SendIcon />}>Send</CustomButton>
```

## Theming

The `CustomButton` component respects the MUI theme settings. You can customize the default look of buttons by adjusting your theme's palette:

```typescript
const theme = createTheme({
  palette: {
    primary: {
      main: '#1976d2',
    },
    secondary: {
      main: '#dc004e',
    },
    // ... other color definitions
  },
});
```

## Notes

- The `primaryColor` and `secondaryColor` props allow you to override the theme colors for a specific button instance. This is useful for one-off custom colored buttons without changing the theme.
- The `rounded` prop creates a pill-shaped button, which can be useful for certain design aesthetics or to make the button stand out.
- Use the `elevation` prop to control the shadow depth of the button, especially useful for "contained" variant buttons.
- The `uppercase` prop can be used to enforce uppercase text, which can be a part of your design system's typography guidelines.

## Accessibility

- Ensure to provide meaningful text for screen readers when using icons as the only content of the button.
- The contrast between the button color and its text should be sufficient to meet accessibility standards.
