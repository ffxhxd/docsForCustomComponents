# CustomInput Component Documentation

## Overview

The `CustomInput` component is a highly customizable input field built on top of Material-UI's TextField component. It offers additional features such as custom validation, error messaging, and clickable input adornments.

## Import

```typescript
import CustomInput from './path/to/CustomInput';
```

## Props

The `CustomInput` component accepts all props from MUI's TextField component, plus the following custom props:

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `validate` | `(value: string) => boolean` | - | Custom validation function |
| `errorMessage` | `string` | 'Invalid input' | Custom error message to display when validation fails |
| `customColor` | `string` | - | Custom background color for the input |
| `startAdornment` | `React.ReactNode` | - | Content to be displayed at the start of the input |
| `endAdornment` | `React.ReactNode` | - | Content to be displayed at the end of the input |
| `startAdornmentClick` | `() => void` | - | Function to be called when the start adornment is clicked |
| `endAdornmentClick` | `() => void` | - | Function to be called when the end adornment is clicked |
| `rounded` | `boolean` | `false` | If `true`, the input will have fully rounded corners |
| `fullWidth` | `boolean` | `false` | If `true`, the input will take up the full width of its container |

## Usage Examples

### Basic Usage

```jsx
<CustomInput label="Username" />
```

### With Custom Validation

```jsx
const validateEmail = (email: string) => {
  const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return re.test(email);
};

<CustomInput 
  label="Email" 
  validate={validateEmail}
  errorMessage="Please enter a valid email address"
/>
```

### With Adornments

```jsx
import { Visibility, VisibilityOff } from '@mui/icons-material';

const [showPassword, setShowPassword] = React.useState(false);

<CustomInput 
  label="Password"
  type={showPassword ? 'text' : 'password'}
  endAdornment={showPassword ? <Visibility /> : <VisibilityOff />}
  endAdornmentClick={() => setShowPassword(!showPassword)}
/>
```

### Custom Styling

```jsx
<CustomInput 
  label="Search"
  rounded
  fullWidth
  customColor="#f0f0f0"
  startAdornment={<SearchIcon />}
/>
```

### With MUI Theme

The `CustomInput` component respects the MUI theme settings. You can customize the default look of inputs by adjusting your theme:

```typescript
const theme = createTheme({
  components: {
    MuiTextField: {
      styleOverrides: {
        root: {
          '& .MuiOutlinedInput-root': {
            '& fieldset': {
              borderColor: 'your-color',
            },
            '&:hover fieldset': {
              borderColor: 'your-hover-color',
            },
            '&.Mui-focused fieldset': {
              borderColor: 'your-focus-color',
            },
          },
        },
      },
    },
  },
});
```

## Notes

- The `validate` prop allows you to pass a custom validation function. This function should return `true` for valid input and `false` for invalid input.
- When validation fails, the `errorMessage` will be displayed.
- The `startAdornment` and `endAdornment` props allow you to add clickable elements to the start and end of the input field respectively.
- Use the `rounded` prop to create a pill-shaped input field.
- The `customColor` prop allows you to set a custom background color for the input field.

## Accessibility

- Ensure to provide meaningful labels for screen readers.
- When using adornments, make sure they have appropriate aria labels for accessibility.
- The contrast between the input text, background, and any error messages should be sufficient to meet accessibility standards.
