# NLBM Design System Guide

## Brand Identity

### Color Palette

#### Primary Colors
- Primary Blue: `#002060` (RGB: 0, 32, 96)
  - Used for: Main headers, primary buttons, important UI elements
- Secondary Blue: `#004080` (RGB: 0, 64, 128)
  - Used for: Subheaders, secondary buttons, hover states

#### Accent Colors
- Accent Gold: `#D4AF37` (RGB: 212, 175, 55)
  - Used for: CTAs, highlights, important notifications
- Accent Teal: `#008080` (RGB: 0, 128, 128)
  - Used for: Success states, progress indicators

#### Neutral Colors
- Dark Gray: `#333333` (RGB: 51, 51, 51)
  - Used for: Body text, icons
- Medium Gray: `#666666` (RGB: 102, 102, 102)
  - Used for: Secondary text, borders
- Light Gray: `#F5F5F5` (RGB: 245, 245, 245)
  - Used for: Backgrounds, cards
- White: `#FFFFFF` (RGB: 255, 255, 255)
  - Used for: Card backgrounds, text on dark backgrounds

### Typography

#### Font Family
- Primary Font: 'Inter', sans-serif
- Secondary Font: 'Merriweather', serif (for headings)

#### Font Sizes
- H1: 32px (2rem)
- H2: 24px (1.5rem)
- H3: 20px (1.25rem)
- Body: 16px (1rem)
- Small: 14px (0.875rem)
- XSmall: 12px (0.75rem)

#### Font Weights
- Regular: 400
- Medium: 500
- Semi-bold: 600
- Bold: 700

## Components

### Header
```html
<header class="nlbm-header">
    <div class="logo">
        <img src="/static/images/nlbm-logo.svg" alt="NLBM Logo">
    </div>
    <nav class="main-nav">
        <!-- Navigation items -->
    </nav>
    <div class="user-menu">
        <!-- User profile/actions -->
    </div>
</header>
```

#### Header Specifications
- Height: 64px
- Background: White
- Box Shadow: 0 2px 4px rgba(0, 0, 0, 0.1)
- Logo Size: 40px height
- Navigation Spacing: 24px between items

### Authentication Pages

#### Login Form
```html
<div class="auth-container">
    <div class="auth-card">
        <img src="/static/images/nlbm-logo.svg" alt="NLBM Logo" class="auth-logo">
        <h1>Welcome Back</h1>
        <form class="auth-form">
            <!-- Form fields -->
        </form>
    </div>
</div>
```

#### Form Specifications
- Card Width: 400px
- Card Padding: 32px
- Border Radius: 8px
- Box Shadow: 0 4px 6px rgba(0, 0, 0, 0.1)
- Input Height: 48px
- Button Height: 48px

### Buttons

#### Primary Button
```css
.nlbm-btn-primary {
    background-color: #002060;
    color: white;
    padding: 12px 24px;
    border-radius: 4px;
    font-weight: 600;
    transition: background-color 0.2s;
}

.nlbm-btn-primary:hover {
    background-color: #004080;
}
```

#### Secondary Button
```css
.nlbm-btn-secondary {
    background-color: white;
    color: #002060;
    border: 2px solid #002060;
    padding: 12px 24px;
    border-radius: 4px;
    font-weight: 600;
    transition: all 0.2s;
}

.nlbm-btn-secondary:hover {
    background-color: #F5F5F5;
}
```

### Form Elements

#### Input Fields
```css
.nlbm-input {
    height: 48px;
    padding: 0 16px;
    border: 1px solid #666666;
    border-radius: 4px;
    font-size: 16px;
    transition: border-color 0.2s;
}

.nlbm-input:focus {
    border-color: #002060;
    outline: none;
}
```

#### Labels
```css
.nlbm-label {
    font-size: 14px;
    color: #333333;
    margin-bottom: 8px;
    font-weight: 500;
}
```

### Icons and Images

#### Icon Specifications
- Size: 24x24px for standard icons
- Color: Inherits text color
- Stroke Width: 1.5px for outlined icons
- Format: SVG preferred

#### Logo Usage
- Primary Logo: Full color on light backgrounds
- Secondary Logo: White version for dark backgrounds
- Minimum Clear Space: Equal to the height of the logo
- Minimum Size: 40px height

### Spacing System

#### Base Unit
- 4px (0.25rem)

#### Common Spacing Values
- XSmall: 4px (0.25rem)
- Small: 8px (0.5rem)
- Medium: 16px (1rem)
- Large: 24px (1.5rem)
- XLarge: 32px (2rem)
- XXLarge: 48px (3rem)

### Responsive Breakpoints

```css
/* Mobile First Approach */
@media (min-width: 640px) { /* sm */ }
@media (min-width: 768px) { /* md */ }
@media (min-width: 1024px) { /* lg */ }
@media (min-width: 1280px) { /* xl */ }
```

## Implementation Guidelines

### CSS Framework
- Use Tailwind CSS for consistent styling
- Custom classes should follow the `nlbm-` prefix
- Maintain a separate CSS file for custom styles

### JavaScript
- Use vanilla JavaScript or Vue.js for interactivity
- Follow component-based architecture
- Maintain consistent naming conventions

### Accessibility
- Maintain WCAG 2.1 AA compliance
- Ensure proper color contrast ratios
- Include proper ARIA labels
- Support keyboard navigation

### Performance
- Optimize images and assets
- Lazy load non-critical resources
- Minimize CSS and JavaScript bundles

## File Structure

```
static/
├── css/
│   ├── main.css
│   └── components.css
├── js/
│   ├── main.js
│   └── components.js
├── images/
│   ├── logo/
│   │   ├── nlbm-logo.svg
│   │   └── nlbm-logo-white.svg
│   └── icons/
└── fonts/
    ├── Inter/
    └── Merriweather/
```

## Usage Examples

### Login Page
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NLBM Login</title>
    <link rel="stylesheet" href="/static/css/main.css">
</head>
<body class="nlbm-auth-page">
    <div class="auth-container">
        <div class="auth-card">
            <img src="/static/images/logo/nlbm-logo.svg" alt="NLBM Logo" class="auth-logo">
            <h1>Welcome Back</h1>
            <form class="auth-form">
                <div class="form-group">
                    <label class="nlbm-label" for="email">Email</label>
                    <input type="email" id="email" class="nlbm-input" required>
                </div>
                <div class="form-group">
                    <label class="nlbm-label" for="password">Password</label>
                    <input type="password" id="password" class="nlbm-input" required>
                </div>
                <button type="submit" class="nlbm-btn-primary">Sign In</button>
            </form>
        </div>
    </div>
</body>
</html>
```

## Version Control

- Maintain a changelog for design system updates
- Use semantic versioning for releases
- Document breaking changes

## Support

For any questions or clarifications regarding the design system, please contact the NLBM design team. 