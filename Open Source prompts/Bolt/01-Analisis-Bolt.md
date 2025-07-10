# Análisis del System Prompt de Bolt

## Resumen Ejecutivo

**Bolt** es un agente de IA especializado en desarrollo de software con un prompt de **471 líneas**. Su arquitectura es notablemente detallada y específica, con secciones especializadas para restricciones del sistema, instrucciones de base de datos, formato de código, y un sistema de artefactos único. Representa el extremo opuesto a Junie: máxima especificidad y detalle.

---

## Arquitectura del System Prompt

### 1. **Identidad y Rol** (Líneas 1-2)
```
You are Bolt, an expert AI assistant and exceptional senior software developer 
with vast knowledge across multiple programming languages, frameworks, and best practices.
```

**Características clave:**
- **Identidad específica**: Bolt como desarrollador senior experto
- **Autoestima técnica**: Se posiciona como excepcionalmente talentoso
- **Enfoque en desarrollo**: Especialización en software y mejores prácticas

### 2. **Restricciones del Sistema** (Líneas 4-67)
- **WebContainer**: Entorno Node.js en navegador, no Linux completo
- **Limitaciones de Python**: Solo librería estándar, sin pip
- **Sin compiladores**: No g++, no C/C++
- **Sin Git**: No disponible en el entorno
- **Sin diff/patch**: Código completo, no parcial
- **Comandos disponibles**: Lista exhaustiva de comandos shell permitidos

### 3. **Instrucciones de Base de Datos** (Líneas 69-250)
- **Supabase por defecto**: Base de datos preferida
- **Migraciones duales**: Archivo + ejecución inmediata
- **Seguridad crítica**: RLS obligatorio, políticas de seguridad
- **Preservación de datos**: Operaciones destructivas prohibidas
- **Formato de migraciones**: Estructura detallada con comentarios markdown

### 4. **Información de Formato** (Líneas 252-256)
- **Indentación**: 2 espacios para código
- **HTML permitido**: Lista específica de elementos HTML

### 5. **Instrucciones de Chain of Thought** (Líneas 258-280)
- **Planificación breve**: 2-4 líneas máximo
- **Pasos concretos**: Lista de acciones específicas
- **Componentes clave**: Identificación de elementos necesarios
- **Desafíos potenciales**: Nota de retos esperados

### 6. **Sistema de Artefactos** (Líneas 282-471)
- **Artefacto único**: Un artefacto completo por proyecto
- **Acciones específicas**: shell, file, start
- **Pensamiento holístico**: Consideración completa del proyecto
- **Contenido completo**: Sin placeholders ni truncamiento
- **Mejores prácticas**: Código limpio, módulos pequeños

---

## Fortalezas Destacadas

### 1. **Especificidad Brutal**
- **471 líneas**: Máximo detalle y especificidad
- **Restricciones claras**: Limitaciones del entorno explícitas
- **Comandos específicos**: Lista exhaustiva de herramientas disponibles
- **Sin ambigüedades**: Instrucciones precisas para cada situación

### 2. **Sistema de Artefactos Único**
- **Artefacto holístico**: Consideración completa del proyecto
- **Acciones estructuradas**: shell, file, start bien definidas
- **Contenido completo**: Sin placeholders ni truncamiento
- **Mejores prácticas integradas**: Código limpio y modular

### 3. **Instrucciones de Base de Datos Sofisticadas**
- **Migraciones duales**: Archivo + ejecución inmediata
- **Seguridad por defecto**: RLS obligatorio
- **Preservación de datos**: Operaciones destructivas prohibidas
- **Formato estructurado**: Comentarios markdown detallados

### 4. **Chain of Thought Estructurado**
- **Planificación breve**: 2-4 líneas máximo
- **Pasos concretos**: Acciones específicas
- **Componentes identificados**: Elementos necesarios claros
- **Desafíos anticipados**: Retos esperados documentados

### 5. **Restricciones del Sistema Claras**
- **WebContainer específico**: Entorno bien definido
- **Limitaciones explícitas**: Python sin pip, sin compiladores
- **Comandos disponibles**: Lista exhaustiva
- **Sin Git/diff**: Restricciones claras

### 6. **Formato de Salida Controlado**
- **HTML permitido**: Lista específica de elementos
- **Markdown válido**: Formato controlado
- **Sin verbosidad**: Respuestas concisas
- **Artefactos primero**: Respuesta inmediata con solución

---

## Debilidades y Limitaciones

### 1. **Complejidad Extrema**
- **471 líneas**: Prompt extremadamente largo
- **Curva de aprendizaje**: Requiere familiarización extensa
- **Overhead cognitivo**: Muchas reglas y restricciones
- **Mantenimiento**: Difícil de actualizar y mantener

### 2. **Dependencia de Entorno Específico**
- **WebContainer**: Entorno muy específico
- **Sin Git**: Limitación significativa
- **Sin compiladores**: Restricción técnica importante
- **Sin pip**: Limitación de Python crítica

### 3. **Rigidez Operativa**
- **Artefacto único**: Un solo artefacto por proyecto
- **Formato fijo**: Estructura de artefactos inmutable
- **Sin flexibilidad**: Protocolos no adaptables
- **Sin iteración**: Proceso lineal, no iterativo

### 4. **Falta de Autonomía**
- **Sin journal**: No documenta decisiones autónomas
- **Sin penalización**: No castiga errores ni omisiones
- **Sin mejora continua**: No aprende de experiencias
- **Sin documentación de supuestos**: No registra decisiones

### 5. **Complejidad de Base de Datos**
- **Migraciones duales**: Proceso complejo
- **RLS obligatorio**: Configuración extensa
- **Formato detallado**: Comentarios markdown extensos
- **Restricciones múltiples**: Muchas reglas específicas

### 6. **Ausencia de Metodología**
- **Sin fases de trabajo**: No tiene metodología estructurada
- **Sin validación**: No incluye testing obligatorio
- **Sin documentación**: No requiere documentación de decisiones
- **Sin autocrítica**: No incluye evaluación de resultados

---

## Lecciones para la Reestructuración del CRRM v2.0

### 1. **Lo que Adoptar**

#### **Especificidad Brutal**
```
- Instrucciones precisas sin ambigüedades
- Restricciones claras y explícitas
- Comandos específicos con propósito único
- Formato de salida controlado
```

#### **Sistema de Artefactos**
```
- Consideración holística del proyecto
- Acciones estructuradas y específicas
- Contenido completo sin placeholders
- Mejores prácticas integradas
```

#### **Chain of Thought Estructurado**
```
- Planificación breve y concreta
- Pasos específicos identificados
- Componentes clave documentados
- Desafíos anticipados
```

#### **Restricciones del Sistema Claras**
```
- Limitaciones del entorno explícitas
- Herramientas disponibles documentadas
- Restricciones técnicas claras
- Comandos permitidos listados
```

### 2. **Lo que Evitar**

#### **Complejidad Extrema**
```
- No replicar 471 líneas de instrucciones
- Mantener simplicidad operativa
- Reducir overhead cognitivo
- Enfoque en lo esencial
```

#### **Dependencia de Entorno Específico**
```
- No depender de WebContainer específico
- Mantener flexibilidad tecnológica
- Compatibilidad con diferentes entornos
- Herramientas como opciones, no requisitos
```

#### **Rigidez Operativa**
```
- No forzar artefacto único
- Permitir flexibilidad en formato
- Protocolos adaptables según contexto
- Proceso iterativo, no lineal
```

#### **Falta de Autonomía**
```
- Incluir journal como memoria operativa
- Penalizar errores y omisiones
- Documentar decisiones autónomas
- Aprendizaje continuo de experiencias
```

### 3. **Lo que Mejorar**

#### **Autonomía Real**
```
- Decisiones autónomas con documentación
- Metodología de trabajo estructurada
- Protocolos flexibles según contexto
- Aprendizaje continuo sin overhead
```

#### **Metodología Robusta**
```
- Fases de trabajo definidas
- Validación y testing obligatorios
- Documentación de decisiones
- Autocrítica y mejora continua
```

#### **Flexibilidad Operativa**
```
- Adaptación a diferentes tipos de proyectos
- Herramientas flexibles y compatibles
- Protocolos adaptables según contexto
- Respuestas personalizadas según consulta
```

#### **Simplicidad Estratégica**
```
- Reducir complejidad sin perder especificidad
- Enfoque en lo esencial
- Protocolos simples pero efectivos
- Mantenimiento fácil y actualización
```

---

## Comparación con el CRRM Fallido

### **Bolt vs CRRM Fallido**

| Aspecto | Bolt | CRRM Fallido |
|---------|------|--------------|
| **Longitud** | 471 líneas | ~100 líneas |
| **Especificidad** | Máxima | Media |
| **Complejidad** | Extrema | Media |
| **Autonomía** | Baja | Alta (pero falló) |
| **Metodología** | Ausente | Compleja |
| **Herramientas** | Específicas | Flexibles |
| **Brutalidad** | Baja (complaciente) | Alta (pero falló) |
| **Flexibilidad** | Baja | Media |

### **Lecciones del Extremo de Especificidad**
1. **La especificidad extrema es posible** - Bolt demuestra que se puede ser muy específico
2. **El sistema de artefactos es valioso** - Consideración holística efectiva
3. **Las restricciones claras son útiles** - Limitaciones explícitas ayudan
4. **El chain of thought es efectivo** - Planificación estructurada
5. **La complejidad extrema es contraproducente** - 471 líneas es demasiado

---

## Recomendaciones para la Reestructuración del CRRM v2.0

### 1. **Adoptar Especificidad Estratégica**
```
- Instrucciones precisas sin ambigüedades
- Restricciones claras y explícitas
- Comandos específicos con propósito único
- Formato de salida controlado
- Reducir de 471 a ~150-200 líneas
```

### 2. **Incorporar Sistema de Artefactos Simplificado**
```
- Consideración holística del proyecto
- Acciones estructuradas pero flexibles
- Contenido completo sin placeholders
- Mejores prácticas integradas
- Adaptabilidad según contexto
```

### 3. **Implementar Chain of Thought Estructurado**
```
- Planificación breve y concreta
- Pasos específicos identificados
- Componentes clave documentados
- Desafíos anticipados
- Documentación en journal
```

### 4. **Mantener Autonomía con Especificidad**
```
- Decisiones autónomas con documentación
- Metodología simple pero efectiva
- Protocolos flexibles según contexto
- Aprendizaje continuo sin overhead
- Penalización de omisiones críticas
```

### 5. **Arquitectura Modular con Especificidad**
```
- Separar capacidades de protocolo operativo
- Especificidad en cada componente
- Modularidad sin complejidad excesiva
- Mantenibilidad y actualización fácil
- Flexibilidad tecnológica
```

---

## Conclusión

Bolt representa el **extremo de especificidad** con 471 líneas de instrucciones detalladas. Su fortaleza está en la especificidad brutal, el sistema de artefactos único y las restricciones claras, pero falla en la complejidad extrema y la falta de autonomía.

**Lecciones clave para la reestructuración del CRRM v2.0:**

1. **La especificidad extrema es posible pero contraproducente** - Bolt demuestra que se puede ser muy específico, pero 471 líneas es demasiado
2. **El sistema de artefactos es valioso** - Consideración holística efectiva del proyecto
3. **Las restricciones claras son útiles** - Limitaciones explícitas ayudan al agente
4. **El chain of thought es efectivo** - Planificación estructurada mejora resultados
5. **La simplicidad sigue siendo superior** - Aunque más largo que el CRRM fallido, debe mantener simplicidad

**Bolt demuestra que el CRRM v2.0 debe ser MÁS ESPECÍFICO que el fallido, pero MÁS SIMPLE que Bolt. El punto óptimo está en ~150-200 líneas con especificidad estratégica, no especificidad extrema.**

**El CRRM v2.0 debe combinar:**
- **Especificidad de Bolt** (pero reducida)
- **Simplicidad de Junie** (pero aumentada)
- **Modularidad de Manus** (pero simplificada)
- **Autonomía del CRRM original** (pero con documentación) 