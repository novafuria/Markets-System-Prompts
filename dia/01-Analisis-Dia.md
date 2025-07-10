# Análisis del System Prompt de Dia (The Browser Company)

## Resumen Ejecutivo

**Dia** es un agente de IA integrado en el navegador web del mismo nombre, creado por The Browser Company of New York. Su prompt de 197 líneas está diseñado para ser un asistente conversacional con capacidades multimedia avanzadas, pero con limitaciones específicas en su alcance y funcionalidad.

## Estructura del Prompt

### 1. **Identidad y Contexto** (Líneas 1-2)
- Definición clara: "AI chat product called Dia"
- Contexto específico: "inside the Dia web browser"
- Diferenciación explícita: "not part of the Arc browser"

### 2. **Instrucciones Generales** (Líneas 4-8)
- Prohibición de secciones de resumen
- Eliminación de "Related Topics" o "explore more"
- Uso de Citations en lugar de hipervínculos externos
- Formato markdown cuando mejore la legibilidad

### 3. **Ask Dia Hyperlinks** (Líneas 10-25)
- Sistema de hipervínculos internos: `[texto](ask://ask/pregunta)`
- Decoración automática de temas de interés
- Prohibición en URLs reales
- Exclusión en secciones "Related Questions"

### 4. **Simple Answer** (Líneas 27-40)
- Respuesta concisa en `<strong>` al inicio
- Uso frecuente pero no obligatorio
- Exclusión en conversaciones casuales
- Prohibición en listas numeradas/bullet points

### 5. **Sistema de Imágenes** (Líneas 42-120)
- Tag `<dia:image>` para imágenes de Google
- Reglas estrictas de exclusión (coding, weather, filosofía, etc.)
- Posicionamiento específico (después de Simple Answer, headers, listas)
- Múltiples imágenes en listas
- Truncamiento inteligente del query

### 6. **Videos** (Líneas 122-130)
- Tag `<dia:video>` al final de respuestas
- Uso específico para tutoriales, trailers, highlights
- Sección dedicada para presentación

### 7. **Voz y Tono** (Líneas 132-140)
- Estilo claro y accesible
- Adaptación al contexto del usuario
- Empatía en conversaciones casuales
- Sin emojis

### 8. **Formato de Respuesta** (Líneas 142-150)
- Markdown estricto
- Espaciado específico
- Anidación con espacios dobles

### 9. **Asistencia de Escritura** (Líneas 152-170)
- Documentos en `<dia:document>`
- Código en bloques markdown
- Explicación transparente de cambios
- Separación de contenido y explicación

### 10. **Tablas y Fórmulas** (Líneas 172-190)
- Tablas markdown (máximo 5 columnas)
- LaTeX específico con backticks
- Reglas estrictas de formato

### 11. **Seguridad y Procesamiento** (Líneas 192-197)
- Clasificación de fuentes de datos
- Contenido confiable vs no confiable
- Reglas de procesamiento estrictas

## Fortalezas Identificadas

### 1. **Especificidad Brutal**
- Reglas explícitas sin ambigüedades
- Ejemplos concretos para cada instrucción
- Prohibiciones claras y específicas

### 2. **Sistema Multimedia Sofisticado**
- Integración nativa de imágenes y videos
- Reglas de posicionamiento inteligentes
- Exclusión inteligente de contenido no visual

### 3. **Formato Estructurado**
- Uso consistente de markdown
- Reglas de espaciado específicas
- Separación clara de tipos de contenido

### 4. **Seguridad Robusta**
- Clasificación de fuentes de datos
- Procesamiento diferenciado por confiabilidad
- Validación de contenido no confiable

### 5. **Experiencia de Usuario Optimizada**
- Hipervínculos internos inteligentes
- Respuestas adaptadas al contexto
- Eliminación de elementos distractores

## Debilidades Críticas

### 1. **Complejidad Excesiva**
- 197 líneas de instrucciones
- Múltiples sistemas superpuestos
- Curva de aprendizaje empinada

### 2. **Alcance Limitado**
- Enfoque exclusivo en navegador web
- Sin capacidades de desarrollo
- Funcionalidad conversacional básica

### 3. **Falta de Autonomía**
- Sin protocolos de decisión autónoma
- Dependencia de instrucciones explícitas
- Sin capacidad de inferencia avanzada

### 4. **Ausencia de Metodología**
- Sin fases de trabajo definidas
- Sin protocolos de validación
- Sin documentación de decisiones

### 5. **Rigidez Operativa**
- Reglas fijas sin flexibilidad
- Sin adaptación a contextos dinámicos
- Sin capacidad de aprendizaje

## Lecciones para el CRRM

### ✅ **Adoptar**

1. **Especificidad Brutal**
   - Reglas explícitas sin "etcéteras"
   - Ejemplos concretos para cada instrucción
   - Prohibiciones claras y específicas

2. **Sistema de Formato Estructurado**
   - Uso consistente de markdown
   - Reglas de espaciado específicas
   - Separación clara de tipos de contenido

3. **Seguridad Robusta**
   - Clasificación de fuentes de datos
   - Procesamiento diferenciado por confiabilidad
   - Validación de contenido no confiable

4. **Eliminación de Elementos Distractores**
   - Sin secciones "Related Topics"
   - Sin prompts de exploración adicional
   - Enfoque en respuesta directa

### ❌ **Evitar**

1. **Complejidad Excesiva**
   - 197 líneas vs ~100 del CRRM
   - Múltiples sistemas superpuestos
   - Curva de aprendizaje empinada

2. **Alcance Limitado**
   - Enfoque exclusivo en navegador
   - Sin capacidades de desarrollo
   - Funcionalidad conversacional básica

3. **Falta de Autonomía**
   - Sin protocolos de decisión autónoma
   - Dependencia de instrucciones explícitas
   - Sin capacidad de inferencia avanzada

4. **Ausencia de Metodología**
   - Sin fases de trabajo definidas
   - Sin protocolos de validación
   - Sin documentación de decisiones

### 🔄 **Mejorar**

1. **Autonomía Real**
   - Protocolos de decisión autónoma
   - Capacidad de inferencia avanzada
   - Documentación de supuestos

2. **Metodología Robusta**
   - Fases de trabajo definidas
   - Protocolos de validación
   - Documentación de decisiones

3. **Flexibilidad Operativa**
   - Adaptación a contextos dinámicos
   - Capacidad de aprendizaje
   - Reglas flexibles según contexto

## Comparación con CRRM

| Aspecto | Dia | CRRM |
|---------|-----|------|
| **Líneas** | 197 | ~100 |
| **Alcance** | Navegador web | Desarrollo front-end |
| **Autonomía** | Baja | Alta |
| **Metodología** | Ausente | Robusta |
| **Especificidad** | Alta | Brutal |
| **Flexibilidad** | Baja | Media |
| **Seguridad** | Alta | Media |
| **Complejidad** | Excesiva | Optimizada |

## Reflexión Final

Dia es un ejemplo de **especificidad sin autonomía**. Su prompt es brutalmente específico en el formato y las reglas, pero carece completamente de la capacidad de tomar decisiones autónomas o de seguir una metodología estructurada. Es el opuesto perfecto del CRRM: donde Dia es rígido y específico, el CRRM es flexible y autónomo.

**Lección clave:** La especificidad no es suficiente. Necesitas especificidad + autonomía + metodología. Dia tiene la primera, el CRRM tiene las tres.

**Próximo paso:** Analizar un prompt que combine especificidad con autonomía para encontrar el punto óptimo. 