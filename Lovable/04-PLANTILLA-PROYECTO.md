# PLANTILLA DE PROYECTO REACT - LOVABLE

## TECNOLOGÍAS BASE

### Stack Principal
- **React 18.3.1**: Framework principal
- **TypeScript 5.5.3**: Type safety
- **Vite 5.4.1**: Build tool y dev server
- **Tailwind CSS 3.4.11**: Framework de estilos
- **React Router DOM 6.26.2**: Navegación

### UI y Componentes
- **shadcn/ui**: Biblioteca de componentes
- **Radix UI**: Componentes primitivos
- **Lucide React**: Iconos
- **Tailwind CSS Animate**: Animaciones

### Estado y Datos
- **@tanstack/react-query 5.56.2**: Gestión de estado del servidor
- **React Hook Form 7.53.0**: Formularios
- **Zod 3.23.8**: Validación de esquemas

### Utilidades
- **clsx + tailwind-merge**: Manejo de clases CSS
- **date-fns 3.6.0**: Manipulación de fechas
- **class-variance-authority**: Variantes de componentes

## ESTRUCTURA DE ARCHIVOS

### Archivos de Configuración
```
├── package.json          # Dependencias y scripts
├── vite.config.ts        # Configuración de Vite
├── tailwind.config.ts    # Configuración de Tailwind
├── eslint.config.js      # Reglas de linting
├── tsconfig.json         # Configuración de TypeScript
└── index.html           # Punto de entrada HTML
```

### Estructura de Código
```
src/
├── main.tsx             # Punto de entrada React
├── App.tsx              # Componente raíz
├── App.css              # Estilos globales
├── index.css            # Estilos de Tailwind
├── vite-env.d.ts        # Tipos de Vite
├── components/          # Componentes UI
│   └── ui/             # Componentes shadcn/ui
├── hooks/               # Custom hooks
├── lib/                 # Utilidades
├── pages/               # Páginas de la aplicación
└── utils/               # Funciones utilitarias
```

## CONFIGURACIÓN ESPECÍFICA

### Vite Configuration
```typescript
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react-swc";
import path from "path";
import { componentTagger } from "lovable-tagger";

export default defineConfig(({ mode }) => ({
  server: {
    host: "::",
    port: 8080,
  },
  plugins: [
    react(),
    mode === 'development' && componentTagger(),
  ].filter(Boolean),
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    },
  },
}));
```

**Características clave**:
- **componentTagger**: Plugin específico de Lovable para desarrollo
- **Alias @**: Para importaciones limpias
- **Puerto 8080**: Puerto por defecto
- **Host ::**: Acceso desde cualquier IP

### Tailwind Configuration
```typescript
export default {
  darkMode: ["class"],
  content: [
    "./pages/**/*.{ts,tsx}",
    "./components/**/*.{ts,tsx}",
    "./app/**/*.{ts,tsx}",
    "./src/**/*.{ts,tsx}",
  ],
  theme: {
    extend: {
      colors: {
        // Sistema de colores CSS variables
        border: 'hsl(var(--border))',
        background: 'hsl(var(--background))',
        foreground: 'hsl(var(--foreground))',
        primary: {
          DEFAULT: 'hsl(var(--primary))',
          foreground: 'hsl(var(--primary-foreground))'
        },
        // ... más colores
      }
    }
  },
  plugins: [require("tailwindcss-animate")],
}
```

**Características clave**:
- **CSS Variables**: Sistema de colores dinámico
- **Dark mode**: Soporte para modo oscuro
- **Animaciones**: Plugin de animaciones
- **Sidebar colors**: Colores específicos para sidebar

### ESLint Configuration
```javascript
import js from "@eslint/js";
import globals from "globals";
import reactHooks from "eslint-plugin-react-hooks";
import reactRefresh from "eslint-plugin-react-refresh";
import tseslint from "typescript-eslint";

export default tseslint.config(
  { ignores: ["dist"] },
  {
    extends: [js.configs.recommended, ...tseslint.configs.recommended],
    files: ["**/*.{ts,tsx}"],
    languageOptions: {
      ecmaVersion: 2020,
      globals: globals.browser,
    },
    plugins: {
      "react-hooks": reactHooks,
      "react-refresh": reactRefresh,
    },
    rules: {
      ...reactHooks.configs.recommended.rules,
      "react-refresh/only-export-components": [
        "warn",
        { allowConstantExport: true },
      ],
      "@typescript-eslint/no-unused-vars": "off",
    },
  }
);
```

**Características clave**:
- **TypeScript ESLint**: Linting específico para TS
- **React Hooks**: Reglas para hooks
- **React Refresh**: Soporte para hot reload
- **Reglas relajadas**: Algunas reglas desactivadas para desarrollo

## COMPONENTES BASE

### App.tsx - Componente Raíz
```typescript
import { Toaster } from "@/components/ui/toaster";
import { Toaster as Sonner } from "@/components/ui/sonner";
import { TooltipProvider } from "@/components/ui/tooltip";
import { QueryClient, QueryClientProvider } from "@tanstack/react-query";
import { BrowserRouter, Routes, Route } from "react-router-dom";
import Index from "./pages/Index";

const queryClient = new QueryClient();

const App = () => (
  <QueryClientProvider client={queryClient}>
    <TooltipProvider>
      <Toaster />
      <Sonner />
      <BrowserRouter>
        <Routes>
          <Route path="/" element={<Index />} />
        </Routes>
      </BrowserRouter>
    </TooltipProvider>
  </QueryClientProvider>
);
```

**Providers incluidos**:
- **QueryClientProvider**: Para React Query
- **TooltipProvider**: Para tooltips
- **BrowserRouter**: Para navegación
- **Toaster/Sonner**: Para notificaciones

### Hooks Personalizados

#### use-mobile.tsx
```typescript
import * as React from "react"

const MOBILE_BREAKPOINT = 768

export function useIsMobile() {
  const [isMobile, setIsMobile] = React.useState<boolean | undefined>(undefined)

  React.useEffect(() => {
    const mql = window.matchMedia(`(max-width: ${MOBILE_BREAKPOINT - 1}px)`)
    const onChange = () => {
      setIsMobile(window.innerWidth < MOBILE_BREAKPOINT)
    }
    mql.addEventListener("change", onChange)
    setIsMobile(window.innerWidth < MOBILE_BREAKPOINT)
    return () => mql.removeEventListener("change", onChange)
  }, [])

  return !!isMobile
}
```

#### use-toast.ts
```typescript
// Hook completo para gestión de toasts
// 192 líneas de código para manejo de notificaciones
```

## SISTEMA DE ESTILOS

### CSS Variables (index.css)
```css
@layer base {
  :root {
    --background: 0 0% 100%;
    --foreground: 222.2 84% 4.9%;
    --card: 0 0% 100%;
    --card-foreground: 222.2 84% 4.9%;
    --popover: 0 0% 100%;
    --popover-foreground: 222.2 84% 4.9%;
    --primary: 222.2 47.4% 11.2%;
    --primary-foreground: 210 40% 98%;
    --secondary: 210 40% 96.1%;
    --secondary-foreground: 222.2 47.4% 11.2%;
    --muted: 210 40% 96.1%;
    --muted-foreground: 215.4 16.3% 46.9%;
    --accent: 210 40% 96.1%;
    --accent-foreground: 222.2 47.4% 11.2%;
    --destructive: 0 84.2% 60.2%;
    --destructive-foreground: 210 40% 98%;
    --border: 214.3 31.8% 91.4%;
    --input: 214.3 31.8% 91.4%;
    --ring: 222.2 84% 4.9%;
    --radius: 0.5rem;
    
    /* Sidebar específico */
    --sidebar-background: 0 0% 98%;
    --sidebar-foreground: 240 5.3% 26.1%;
    --sidebar-primary: 240 5.9% 10%;
    --sidebar-primary-foreground: 0 0% 98%;
    --sidebar-accent: 240 4.8% 95.9%;
    --sidebar-accent-foreground: 240 5.9% 10%;
    --sidebar-border: 220 13% 91%;
    --sidebar-ring: 217.2 91.2% 59.8%;
  }

  .dark {
    /* Variables para modo oscuro */
    --background: 222.2 84% 4.9%;
    --foreground: 210 40% 98%;
    /* ... más variables dark */
  }
}
```

## DEPENDENCIAS ESPECÍFICAS

### Dependencias Principales
- **@hookform/resolvers**: Para validación de formularios
- **@radix-ui/react-***: Componentes primitivos
- **@tanstack/react-query**: Gestión de estado del servidor
- **class-variance-authority**: Variantes de componentes
- **clsx**: Utilidad para clases CSS
- **cmdk**: Comando palette
- **date-fns**: Manipulación de fechas
- **embla-carousel-react**: Carousel
- **input-otp**: Input OTP
- **lucide-react**: Iconos
- **next-themes**: Gestión de temas
- **react-day-picker**: Selector de fechas
- **react-hook-form**: Formularios
- **react-resizable-panels**: Paneles redimensionables
- **react-router-dom**: Navegación
- **recharts**: Gráficos
- **sonner**: Notificaciones toast
- **tailwind-merge**: Merge de clases Tailwind
- **tailwindcss-animate**: Animaciones
- **vaul**: Drawer component
- **zod**: Validación de esquemas

### Dependencias de Desarrollo
- **@eslint/js**: ESLint base
- **@tailwindcss/typography**: Tipografía
- **@types/node**: Tipos de Node.js
- **@types/react**: Tipos de React
- **@types/react-dom**: Tipos de React DOM
- **@vitejs/plugin-react-swc**: Plugin React para Vite
- **autoprefixer**: Autoprefixer CSS
- **eslint**: Linter
- **eslint-plugin-react-hooks**: Reglas para hooks
- **eslint-plugin-react-refresh**: Reglas para hot reload
- **globals**: Variables globales
- **lovable-tagger**: Plugin específico de Lovable
- **postcss**: PostCSS
- **tailwindcss**: Tailwind CSS
- **typescript**: TypeScript
- **typescript-eslint**: ESLint para TypeScript

## CARACTERÍSTICAS ESPECIALES

### Lovable Tagger
- **Plugin específico**: Solo en modo desarrollo
- **Component tagging**: Para identificación de componentes
- **Debugging**: Ayuda en desarrollo

### Sistema de Colores
- **CSS Variables**: Sistema dinámico
- **Dark/Light mode**: Soporte completo
- **Sidebar específico**: Colores para sidebar
- **HSL**: Uso de HSL para colores

### Configuración de Desarrollo
- **Hot reload**: Recarga automática
- **TypeScript**: Type checking en tiempo real
- **ESLint**: Linting automático
- **Alias @**: Importaciones limpias 