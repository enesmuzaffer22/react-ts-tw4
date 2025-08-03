# React + TypeScript + Tailwind CSS 4 Boilerplate

A minimal React + Vite + TypeScript + Tailwind CSS 4 boilerplate template for quick project setup.

## 🚀 Quick Start with degit

### English

You can quickly clone this template using [degit](https://github.com/Rich-Harris/degit):

```bash
# Install degit globally (if not already installed)
npm install -g degit

# Clone this template
degit enesmuzaffer22/react-ts-tw4 my-new-project

# Navigate to your project
cd my-new-project

# Install dependencies
npm install

# Start development server
npm run dev
```

### Türkçe

Bu şablonu [degit](https://github.com/Rich-Harris/degit) kullanarak hızlıca klonlayabilirsiniz:

```bash
# degit'i global olarak yükleyin (eğer yüklü değilse)
npm install -g degit

# Bu şablonu klonlayın
degit enesmuzaffer22/react-ts-tw4 yeni-projem

# Proje klasörüne gidin
cd yeni-projem

# Bağımlılıkları yükleyin
npm install

# Geliştirme sunucusunu başlatın
npm run dev
```

## 📦 What's Included / İçerikler

- ⚡ **Vite** - Fast build tool
- ⚛️ **React 18** - Latest React version
- 🔷 **TypeScript** - Type safety and better development experience
- 🎨 **Tailwind CSS 4** - Latest Tailwind version
- 📝 **ESLint** - Code linting with TypeScript support
- 🔥 **Hot Module Replacement** - Fast refresh during development

## 🛠️ Development

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## 📋 Available Scripts / Kullanılabilir Komutlar

```bash
npm run dev          # Start development server / Geliştirme sunucusunu başlat
npm run build        # Build for production / Üretim için derle
npm run preview      # Preview production build / Üretim derlemesini önizle
npm run lint         # Run ESLint / ESLint çalıştır
```

## 🔧 Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default tseslint.config([
  globalIgnores(["dist"]),
  {
    files: ["**/*.{ts,tsx}"],
    extends: [
      // Other configs...

      // Remove tseslint.configs.recommended and replace with this
      ...tseslint.configs.recommendedTypeChecked,
      // Alternatively, use this for stricter rules
      ...tseslint.configs.strictTypeChecked,
      // Optionally, add this for stylistic rules
      ...tseslint.configs.stylisticTypeChecked,

      // Other configs...
    ],
    languageOptions: {
      parserOptions: {
        project: ["./tsconfig.node.json", "./tsconfig.app.json"],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
]);
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from "eslint-plugin-react-x";
import reactDom from "eslint-plugin-react-dom";

export default tseslint.config([
  globalIgnores(["dist"]),
  {
    files: ["**/*.{ts,tsx}"],
    extends: [
      // Other configs...
      // Enable lint rules for React
      reactX.configs["recommended-typescript"],
      // Enable lint rules for React DOM
      reactDom.configs.recommended,
    ],
    languageOptions: {
      parserOptions: {
        project: ["./tsconfig.node.json", "./tsconfig.app.json"],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
]);
```
