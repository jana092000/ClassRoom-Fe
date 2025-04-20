# React Project Structure Documentation

## Overview

This document outlines the standard folder structure for our React application. Following this structure helps ```maintain consistency, improves developer experience```, and makes the codebase more navigable.

## Directory Structure

```
project-root/
├── docs/                     # Project documentation
│   ├── architecture.md       # System architecture decisions
│   ├── project-structure.md  # This file
│   ├── coding-standards.md   # Code style and patterns
│   ├── deployment.md         # Deployment procedures
│   └── assets/               # Documentation assets (images, diagrams)
│
├── public/                   # Static files
│   ├── index.html            # HTML entry point
│   ├── favicon.ico           # Site favicon
│   ├── robots.txt            # SEO control
│   └── manifest.json         # PWA manifest
│
├── src/                      # Source code
│   ├── assets/               # Static assets for the application
│   │   ├── images/           # Image files
│   │   ├── fonts/            # Font files
│   │   └── styles/           # Global styles
│   │
│   ├── components/           # Reusable UI components
│   │   ├── common/           # Shared across multiple features
│   │   │   ├── Button/
│   │   │   │   ├── Button.jsx           # Component implementation
│   │   │   │   ├── Button.test.js       # Component tests
│   │   │   │   ├── Button.module.css    # Component-specific styles
│   │   │   │   ├── Button.stories.js    # Storybook stories
│   │   │   │   └── README.md            # Component documentation
│   │   │   └── ...
│   │   │
│   │   └── layout/           # Application layout components
│   │       ├── Header/
│   │       ├── Footer/
│   │       ├── Sidebar/
│   │       ├── Navbar/
│   │       └── ...
│   │
│   ├── hooks/                # Custom React hooks
│   │   ├── useForm.js
│   │   ├── useForm.test.js
│   │   ├── useForm.md        # Hook documentation
│   │   └── ...
│   │
│   ├── pages/                # Page components
│   │   ├── Home/
│   │   │   ├── Home.jsx
│   │   │   ├── Home.test.js
│   │   │   ├── Home.module.css
│   │   │   └── components/   # Page-specific components
│   │   └── ...
│   │
│   ├── services/             # API services
│   │   ├── api.js            # API client setup
│   │   ├── auth.service.js   # Authentication service
│   │   └── ...
│   │
│   ├── utils/                # Utility functions
│   │   ├── helpers.js        # General helpers
│   │   ├── constants.js      # Application constants
│   │   ├── formatters.js     # Data formatting utilities
│   │   └── ...
│   │
│   ├── context/              # React Context providers
│   │   ├── AuthContext.js
│   │   ├── ThemeContext.js
│   │   └── ...
│   │
│   ├── store/                # State management (Redux/Zustand)
│   │   ├── slices/           # Redux slices or equivalent
│   │   ├── actions/
│   │   ├── reducers/
│   │   └── index.js
│   │
│   ├── types/                # TypeScript type definitions
│   │   ├── api.types.ts
│   │   └── ...
│   │
│   ├── App.jsx               # Main application component
│   ├── index.jsx             # Application entry point
│   └── routes.js             # Route definitions
│
├── .storybook/              # Storybook configuration
├── .github/                 # GitHub templates and workflows
├── config/                  # Configuration files for build tools
│
├── .gitignore               # Git ignore file
├── .eslintrc.js             # ESLint configuration
├── .prettierrc              # Prettier configuration
├── jest.config.js           # Jest configuration
├── tailwind.config.js       # Tailwind CSS configuration (if applicable)
├── tsconfig.json            # TypeScript configuration (if applicable)
│
├── CONTRIBUTING.md          # Contribution guidelines
├── README.md                # Project overview and setup instructions
├── CHANGELOG.md             # Version history
├── LICENSE                  # License information
│
├── package.json             # Dependencies and scripts
└── package-lock.json        # Locked dependencies
```

## Directory Purposes

### `/docs`
Contains comprehensive project documentation. Keep files focused on specific topics and use markdown for better readability.

### `/public`
Contains static assets that don't require processing by webpack. Files here are copied directly to the build output.

### `/src`
Contains all source code for the application.

#### `/src/assets`
Static files like images, fonts, and global styles used throughout the application.

#### `/src/components`
Reusable UI components. Each component should have its own directory with related files:
- Component implementation (.jsx or .tsx)
- Tests (.test.js or .test.tsx)
- Component-specific styles (.module.css, .scss, etc.)
- Storybook stories (.stories.js)
- README.md with usage documentation

Components are organized into:
- **common/**: Shared components used across multiple features
- **layout/**: Components that define the application's structure

#### `/src/hooks`
Custom React hooks with their tests and documentation.

#### `/src/pages`
Components that represent entire pages in the application. Each page can have its own subdirectory with page-specific components.

#### `/src/services`
API calls and other external service integrations.

#### `/src/utils`
Helper functions, constants, and utility code.

#### `/src/context`
React Context providers for state management that spans multiple components.

#### `/src/store`
State management setup using Redux, Zustand, or similar libraries.

#### `/src/types`
TypeScript type definitions (for TypeScript projects).

### Configuration Files
Configuration files for various tools are kept at the root level for easy access.

## File Naming Conventions

- **Component files**: Use PascalCase (e.g., `Button.jsx`, `UserProfile.tsx`)
- **Non-component files**: Use camelCase (e.g., `api.js`, `useForm.js`)
- **Test files**: Append `.test.js` or `.test.tsx` to the name of the file being tested
- **Style files**: Use the same name as the component with appropriate extension (e.g., `Button.module.css`)

## Component Structure

Each component directory should follow this structure:

```
ComponentName/
├── ComponentName.jsx        # Implementation
├── ComponentName.test.js    # Tests
├── ComponentName.module.css # Styles
├── ComponentName.stories.js # Storybook (optional)
└── README.md                # Documentation
```

## Best Practices

1. **Component Isolation**: Each component should be self-contained with its own tests and styles.

2. **Documentation First**: Document the purpose and usage of components and important functions.

3. **Feature-Based Organization**: For larger applications, consider organizing by feature rather than by technical concern.

4. **Consistent Imports**: Use consistent import patterns throughout the application.

5. **Lazy Loading**: Use React.lazy() for code-splitting on routes and large components.

6. **Testing**: Maintain high test coverage for components and utility functions.

7. **Type Safety**: Use PropTypes or TypeScript to ensure type safety.