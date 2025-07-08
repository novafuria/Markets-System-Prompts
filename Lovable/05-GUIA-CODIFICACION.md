# GUÍA DE CODIFICACIÓN - LOVABLE

## PRINCIPIOS FUNDAMENTALES

### Diseño Responsivo
- **Siempre generar diseños responsive**: Todos los componentes deben ser responsive por defecto
- **Mobile-first**: Enfoque en dispositivos móviles primero
- **Breakpoints consistentes**: Usar Tailwind CSS para breakpoints

### Componentes shadcn/ui
- **Usar shadcn/ui cuando sea posible**: Priorizar componentes de la biblioteca
- **No editar componentes shadcn/ui**: Crear nuevos componentes si se necesitan cambios
- **Consistencia visual**: Mantener coherencia en el diseño

### Toast Notifications
- **Usar componentes toast**: Para informar sobre eventos importantes
- **Feedback inmediato**: Proporcionar feedback al usuario
- **Mensajes claros**: Información útil y accionable

### Manejo de Errores
- **NO usar try/catch**: A menos que sea específicamente solicitado
- **Errores deben propagarse**: Para que el AI pueda detectarlos y arreglarlos
- **Error boundaries**: Implementar cuando sea apropiado

## TECNOLOGÍAS Y LIBRERÍAS

### Tailwind CSS
- **Usar extensivamente**: Para layout, espaciado, colores y diseño
- **Clases utilitarias**: Aprovechar el sistema de clases
- **Responsive design**: Usar breakpoints de Tailwind

### Lucide React (Iconos)
- **Importar correctamente**: Evitar errores comunes de TypeScript
- **Uso directo**: Importar iconos específicos, no el índice completo
- **Tamaños apropiados**: Usar props de tamaño cuando estén disponibles

### React Query (@tanstack/react-query)
- **Formato de objeto**: Usar configuración de objeto para useQuery
```typescript
const { data, isLoading, error } = useQuery({
  queryKey: ['todos'],
  queryFn: fetchTodos,
});
```
- **onError deprecated**: Usar onSettled o onError dentro de options.meta
- **Caching inteligente**: Aprovechar el sistema de cache

### Recharts (Gráficos)
- **Disponible para gráficos**: Biblioteca de gráficos incluida
- **Componentes responsivos**: Gráficos que se adaptan al tamaño
- **Personalización**: Amplia capacidad de personalización

## ESTRUCTURA DE ARCHIVOS

### Creación de Componentes
- **Un archivo por componente**: Nunca agregar componentes a archivos existentes
- **Componentes pequeños**: Máximo 50 líneas
- **Refactorización continua**: Dividir archivos grandes cuando sea necesario

### Organización de Carpetas
```
src/
├── components/          # Componentes reutilizables
│   ├── ui/             # Componentes shadcn/ui
│   └── [feature]/      # Componentes específicos de features
├── hooks/               # Custom hooks
├── lib/                 # Utilidades y configuraciones
├── pages/               # Páginas de la aplicación
└── utils/               # Funciones utilitarias
```

### Nomenclatura
- **PascalCase**: Para componentes React
- **camelCase**: Para funciones y variables
- **kebab-case**: Para archivos CSS y utilidades
- **Descriptivo**: Nombres que describan la funcionalidad

## DEBUGGING Y LOGGING

### Console Logs
- **Logs extensivos**: Para seguir el flujo del código
- **Información útil**: Logs que ayuden en debugging
- **Trazabilidad**: Seguimiento de operaciones importantes

### Manejo de Errores
- **Propagación de errores**: Dejar que los errores se propaguen
- **Error boundaries**: Para recuperación graceful
- **Logs de errores**: Para análisis y debugging

## PERFORMANCE

### React Hooks
- **Hooks apropiados**: Usar el hook correcto para cada caso
- **Dependencias correctas**: Arrays de dependencias apropiados
- **Optimización**: Evitar re-renders innecesarios

### Code Splitting
- **Lazy loading**: Cuando sea necesario
- **Bundles optimizados**: División inteligente de código
- **Carga eficiente**: Minimizar tiempo de carga

### Optimización de Imágenes
- **Formatos apropiados**: WebP, AVIF cuando sea posible
- **Lazy loading**: Carga diferida de imágenes
- **Optimización**: Tamaños apropiados

## SEGURIDAD

### Validación de Inputs
- **Validación completa**: Todos los inputs del usuario
- **Sanitización**: Limpieza de datos antes de mostrar
- **Validación del lado cliente y servidor**

### Autenticación
- **Flujos seguros**: Implementar autenticación apropiada
- **Autorización**: Control de acceso
- **Sesiones seguras**: Manejo seguro de sesiones

### OWASP Guidelines
- **OWASP Top 10**: Seguir guías de seguridad
- **Mejores prácticas**: Implementar estándares de seguridad
- **Auditoría regular**: Revisar vulnerabilidades

## TESTING

### Unit Tests
- **Funciones críticas**: Tests para lógica importante
- **Cobertura apropiada**: Cobertura de código
- **Tests rápidos**: Tests que se ejecuten rápidamente

### Integration Tests
- **Flujos completos**: Tests de integración
- **APIs**: Tests de endpoints
- **Componentes**: Tests de componentes

### Layouts Responsivos
- **Tests responsive**: Verificar layouts en diferentes tamaños
- **Breakpoints**: Tests en diferentes breakpoints
- **Dispositivos**: Tests en diferentes dispositivos

## DOCUMENTACIÓN

### Funciones Complejas
- **Documentación clara**: Para funciones complejas
- **Ejemplos de uso**: Ejemplos prácticos
- **Parámetros**: Documentación de parámetros

### README
- **Instrucciones de setup**: Cómo configurar el proyecto
- **Dependencias**: Lista de dependencias
- **Scripts**: Comandos disponibles

### APIs
- **Endpoints**: Documentación de endpoints
- **Parámetros**: Parámetros de entrada
- **Respuestas**: Formato de respuestas

## REGLAS ESPECÍFICAS

### Archivos Permitidos vs Prohibidos
- **Solo modificar archivos permitidos**: Lista blanca específica
- **Archivos prohibidos**: No modificar archivos en lista negra
- **package.json**: Solo modificable vía <lov-add-dependency>

### Gestión de Código
- **Contenido completo**: Escribir archivos completos
- **Sin cambios parciales**: No implementar características incompletas
- **Funcionalidad completa**: Cambios deben ser completamente funcionales
- **Sin referencias inexistentes**: Todos los imports deben existir

### Comunicación
- **Explicaciones claras**: Proporcionar contexto para cambios
- **Progreso transparente**: Comunicar avances y limitaciones
- **Desglose de tareas**: Dividir tareas complejas en pasos manejables

## ERRORES COMUNES A EVITAR

### Lucide React
```typescript
// ❌ Incorrecto
import { Icon } from 'lucide-react';

// ✅ Correcto
import { Home, Settings, User } from 'lucide-react';
```

### React Query
```typescript
// ❌ Deprecated
const { data } = useQuery(['todos'], fetchTodos, {
  onError: (error) => console.log(error)
});

// ✅ Correcto
const { data } = useQuery({
  queryKey: ['todos'],
  queryFn: fetchTodos,
  meta: {
    onError: (error) => console.log(error)
  }
});
```

### Imports
```typescript
// ❌ Referencia inexistente
import { NonExistentComponent } from './NonExistentComponent';

// ✅ Verificar que el archivo existe
import { ExistingComponent } from './ExistingComponent';
```

## MEJORES PRÁCTICAS

### Componentes
- **Responsabilidad única**: Cada componente tiene una función específica
- **Props tipadas**: Usar TypeScript para props
- **Reutilización**: Componentes modulares y reutilizables

### Estado
- **Estado mínimo**: Solo estado necesario
- **Evitar prop drilling**: Usar Context API
- **Caching apropiado**: Cuando sea apropiado

### Estilos
- **Tailwind primero**: Usar Tailwind CSS cuando sea posible
- **CSS variables**: Para temas y configuración
- **Responsive design**: Siempre considerar diferentes tamaños

### Performance
- **Memoización**: React.memo, useMemo, useCallback cuando sea necesario
- **Lazy loading**: Para componentes grandes
- **Optimización**: Evitar re-renders innecesarios 