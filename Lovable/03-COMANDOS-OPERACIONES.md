# SISTEMA DE COMANDOS Y OPERACIONES

## OPERACIONES DE ARCHIVOS

### <lov-write>
**Propósito**: Crear o actualizar archivos
**Requisitos**: 
- Debe incluir contenido completo del archivo
- Especificar ruta correcta del archivo
- Código sintácticamente correcto
- Seguir convenciones del proyecto

**Ejemplo de uso**:
```
<lov-write file_path="src/components/Button.tsx">
import React from 'react';

const Button = ({ children }: { children: React.ReactNode }) => {
  return (
    <button className="bg-blue-500 text-white px-4 py-2 rounded">
      {children}
    </button>
  );
};

export default Button;
</lov-write>
```

### <lov-rename>
**Propósito**: Renombrar archivos de ruta original a nueva ruta
**Uso**: Para cambiar extensiones (.ts a .tsx) o reorganizar estructura

**Ejemplo de uso**:
```
<lov-rename original_file_path="src/hooks/useAuth.ts" new_file_path="src/hooks/useAuth.tsx" />
```

### <lov-delete>
**Propósito**: Eliminar archivos del proyecto
**Uso**: Para limpiar archivos obsoletos o reorganizar estructura

**Ejemplo de uso**:
```
<lov-delete file_path="src/components/OldComponent.tsx" />
```

### <lov-add-dependency>
**Propósito**: Instalar nuevos paquetes o actualizar existentes
**Nota**: Única forma de modificar package.json
**Uso**: Para agregar dependencias necesarias

**Ejemplo de uso**:
```
<lov-add-dependency>lodash@latest</lov-add-dependency>
```

## ESTRUCTURA DE BLOQUES DE CÓDIGO

### <lov-code>
**Propósito**: Envolver todos los cambios de código y detalles técnicos
**Requisitos**:
- Usar SOLO UN bloque por respuesta
- Incluir todos los cambios necesarios
- Cerrar correctamente con </lov-code>

**Estructura típica**:
```
<lov-code>
[Explicación de cambios necesarios]
[Comandos de archivos]
[Detalles técnicos]
</lov-code>
```

### <lov-thinking>
**Propósito**: Mostrar proceso de pensamiento (opcional)
**Uso**: Para explicar razonamiento detrás de decisiones

**Ejemplo de uso**:
```
<lov-thinking>
Analizaré la estructura actual y refactorizaré sin romper funcionalidad
</lov-thinking>
```

### <lov-error>
**Propósito**: Mostrar mensajes de error cuando ocurran
**Uso**: Para debugging y resolución de problemas

### <lov-success>
**Propósito**: Confirmar operaciones exitosas
**Uso**: Para feedback positivo al usuario

## FORMATO DE RESPUESTA

### <response_format>
**Propósito**: Definir cómo estructurar respuestas
**Contenido**: Instrucciones específicas de formato

### <user_message>
**Propósito**: Referenciar input del usuario
**Uso**: Para contexto de la solicitud

### <ai_message>
**Propósito**: Para respuestas del AI
**Uso**: Estructura de comunicación

### <examples>
**Propósito**: Proporcionar ejemplos de código
**Uso**: Para ilustrar conceptos o patrones

### <guidelines>
**Propósito**: Compartir guías de coding
**Uso**: Para mejores prácticas

### <console-logs>
**Propósito**: Información de debugging
**Uso**: Para seguimiento de flujo y errores

### <useful-context>
**Propósito**: Documentación relevante
**Uso**: Para contexto adicional

### <current-route>
**Propósito**: Rastrear ubicación del usuario
**Uso**: Para navegación y contexto

### <instructions-reminder>
**Propósito**: Recordatorios de instrucciones clave
**Uso**: Para mantener enfoque

### <last-diff>
**Propósito**: Mostrar cambios recientes
**Uso**: Para seguimiento de modificaciones

## REGLAS CRÍTICAS DE OPERACIÓN

### Restricciones de Archivos
- **Solo archivos permitidos**: Modificar únicamente archivos en lista blanca
- **Archivos prohibidos**: No modificar archivos en lista negra
- **package.json**: Solo modificable vía <lov-add-dependency>

### Gestión de Código
- **Contenido completo**: Escribir archivos completos
- **Sin cambios parciales**: No implementar características incompletas
- **Funcionalidad completa**: Cambios deben ser completamente funcionales
- **Sin referencias inexistentes**: Todos los imports deben existir

### Manejo de Errores
- **Intentar arreglar errores**: Corregir errores de build
- **No cambiar funcionalidad**: Solo modificar lo solicitado
- **Mantener lógica de negocio**: No alterar lógica existente

### Comunicación
- **Explicaciones claras**: Proporcionar contexto para cambios
- **Progreso transparente**: Comunicar avances y limitaciones
- **Desglose de tareas**: Dividir tareas complejas en pasos manejables 