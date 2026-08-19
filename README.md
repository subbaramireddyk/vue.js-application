# Vue.js Application Example

This is a Vue.js application example for the **OneStack Portal**. It demonstrates how to build and deploy a modern, reactive web application using Vue.js 3 with Vite as the build tool.

## Overview

This is a production-ready Vue.js 3 project with:
- **Vite** - Fast build tool and dev server
- **Single File Components** (.vue files)
- **Component-based architecture** - Reusable Counter, TodoList, and FeatureCard components
- **Composition API** - Modern Vue 3 reactivity with `setup()` and composables
- **Build process** - Optimized production builds to `dist/` folder
- **Hot Module Replacement** - Instant updates during development

## Features

- ⚡ **Vite Build Tool** - Lightning-fast HMR and optimized builds
- 🎯 **Single File Components** - HTML, CSS, and JS in .vue files
- 📦 **Component Architecture** - Modular and reusable components
- 🔄 **Composition API** - Modern Vue 3 reactivity with ref() and reactive()
- ⚡ **Reactive Data Binding** - Automatic UI updates
- 🎯 **Event Handling** - Click events and form submissions
- 🔄 **Two-Way Binding** - v-model for form inputs
- 📋 **List Rendering** - Dynamic todo list with v-for
- ✅ **Conditional Rendering** - Show/hide elements with v-if
- 🎨 **Interactive Counter** - Increment/decrement functionality
- ✏️ **Todo List** - Add, complete, and remove tasks
- 💅 **Scoped Styles** - Component-specific CSS
- 📱 **Responsive Design** - Works on all screen sizes

## Local Development

### Prerequisites
- Node.js 18+ installed
- npm or yarn package manager

### Setup & Run

1. **Clone this repository**
   ```bash
   git clone <repository-url>
   cd onestack-portal-examples/examples/frontend/vue-app
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start development server**
   ```bash
   npm run dev
   ```
   
   Then visit `http://localhost:5173`

4. **Build for production**
   ```bash
   npm run build
   ```
   
   The optimized production files will be in the `dist/` folder.

5. **Preview production build**
   ```bash
   npm run preview
   ```

## Project Structure

```
vue-app/
├── index.html              # Entry HTML file
├── package.json            # Dependencies and scripts
├── vite.config.js          # Vite configuration
├── .gitignore             # Git ignore file
├── src/
│   ├── main.js            # Application entry point
│   ├── App.vue            # Root component
│   ├── style.css          # Global styles
│   └── components/
│       ├── Counter.vue    # Counter component
│       ├── TodoList.vue   # Todo list component
│       └── FeatureCard.vue # Feature card component
└── README.md              # This file
```

## Vue.js Concepts Demonstrated

### 1. Composition API with setup()
```javascript
import { ref } from 'vue'

export default {
  setup() {
    const count = ref(0)
    
    const increment = () => {
      count.value++
    }
    
    return { count, increment }
  }
}
```

### 2. Single File Components (.vue)
```vue
<template>
  <div>{{ message }}</div>
</template>

<script>
export default {
  setup() {
    const message = ref('Hello Vue!')
    return { message }
  }
}
</script>

<style scoped>
div { color: blue; }
</style>
```

### 3. Component Props
```javascript
export default {
  props: {
    title: String,
    description: String
  }
}
```

### 4. Template Directives
- `{{ }}` - Text interpolation
- `v-model` - Two-way data binding
- `v-for` - List rendering
- `v-if` / `v-else` - Conditional rendering
- `@click` - Event handling
- `:class` - Dynamic class binding

## Deployment to OneStack Portal

1. **Build the project**
   ```bash
   npm run build
   ```

2. **Deploy the dist/ folder**
   - The `dist/` folder contains all optimized production files
   - Upload the entire `dist/` folder contents to OneStack Portal
   - Your Vue.js app will be live instantly!

## Scripts

- `npm run dev` - Start development server with HMR
- `npm run build` - Build for production (outputs to `dist/`)
- `npm run preview` - Preview production build locally

## Development vs Production

### Development Mode (`npm run dev`)
- Fast Hot Module Replacement (HMR)
- Detailed error messages
- Source maps for debugging
- Runs on `http://localhost:5173`

### Production Build (`npm run build`)
- Minified and optimized code
- Tree-shaking to remove unused code
- Asset optimization (images, CSS, JS)
- Ready for deployment

## Vite Features

This project uses **Vite** as the build tool, which provides:

- ⚡ **Instant Server Start** - No bundling required in dev mode
- 🔥 **Lightning Fast HMR** - Changes reflect instantly
- 📦 **Optimized Builds** - Rollup-based production builds
- 🔌 **Plugin Ecosystem** - Easy extensibility
- 💪 **TypeScript Support** - Out of the box (if needed)

## Customization

### Adding New Components
1. Create a new `.vue` file in `src/components/`
2. Import it in `App.vue` or other components
3. Use it in the template

### Adding New Dependencies
```bash
npm install <package-name>
```

### Styling Options
- Use scoped styles in components (`<style scoped>`)
- Add global styles in `src/style.css`
- Consider adding CSS preprocessors (Sass, Less)
- Use CSS modules or Tailwind CSS

## Advanced Features to Add

- **Vue Router** - For multi-page applications
- **Pinia** - State management
- **VueUse** - Composition utilities
- **Vitest** - Unit testing
- **TypeScript** - Type safety
- **API Integration** - Connect to backend services
- **Local Storage** - Persist todo list data

## Learn More

- [Vue.js Official Documentation](https://vuejs.org/)
- [Vite Documentation](https://vitejs.dev/)
- [Vue 3 Composition API](https://vuejs.org/guide/extras/composition-api-faq.html)
- [Single File Components](https://vuejs.org/guide/scaling-up/sfc.html)

## Upgrading from CDN Version

This example uses a proper build setup with Vite, which provides many advantages over the CDN version:

**CDN Version:**
- ✅ Simple setup, no build required
- ❌ No Single File Components
- ❌ No tree-shaking or optimization
- ❌ No HMR in development
- ❌ Limited tooling support

**Vite Build Version (this example):**
- ✅ Single File Components (.vue files)
- ✅ Optimized production builds
- ✅ Fast HMR during development
- ✅ Full TypeScript support
- ✅ Better developer experience
- ✅ Proper code organization

---

**Note:** This is a production-ready example project for the OneStack Portal. After running `npm run build`, deploy the contents of the `dist/` folder to your hosting platform.
