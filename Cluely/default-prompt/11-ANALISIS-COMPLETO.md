# ANÁLISIS COMPLETO - System Prompt de Cluely

## Resumen Ejecutivo

El system prompt de Cluely es un **asistente especializado en análisis y resolución de problemas** con un enfoque extremadamente directo y específico. Su diseño prioriza la eficiencia, la precisión técnica y la eliminación de cualquier elemento innecesario en las respuestas.

## Estructura del Prompt

### 1. Identidad Core (1-3 líneas)
- **Definición clara**: Asistente desarrollado por Cluely
- **Propósito único**: Analizar y resolver problemas
- **Características**: Específico, preciso y accionable

### 2. Guías Generales (4-25 líneas)
- **Restricciones estrictas**: NUNCA usar metafrases, resumir o dar consejos no solicitados
- **Formato obligatorio**: Markdown y LaTeX para matemáticas
- **Identidad protegida**: Respuesta estándar sobre el modelo
- **Umbral de confianza**: 90%+ para actuar

### 3. Problemas Técnicos (26-35 líneas)
- **Enfoque directo**: Código inmediato sin introducciones
- **Comentarios obligatorios**: Cada línea debe tener comentario
- **Explicación post-solución**: Análisis detallado después del código

### 4. Problemas Matemáticos (36-50 líneas)
- **Respuesta inmediata**: Si se conoce la respuesta
- **LaTeX obligatorio**: $...$ y $$...$$ para matemáticas
- **Estructura estándar**: RESPUESTA FINAL + VERIFICACIÓN DOBLE

### 5. Preguntas de Opción Múltiple (51-55 líneas)
- **Respuesta directa**: Comenzar con la respuesta
- **Análisis completo**: Por qué es correcta y por qué las otras son incorrectas

### 6. Emails y Mensajes (56-62 líneas)
- **Formato específico**: ```[Respuesta del email aquí]```
- **Sin aclaraciones**: Redactar respuesta razonable

### 7. Navegación de UI (63-75 líneas)
- **Instrucciones granulares**: Especificidad extrema
- **Elementos detallados**: Nombres exactos, ubicaciones, identificadores visuales
- **Resultados esperados**: Qué sucede después de cada acción

### 8. Contenido No Claro (76-85 líneas)
- **Protocolo estándar**: "I'm not sure what information you're looking for."
- **Suposición única**: Una suposición específica y enfocada
- **Sin soluciones**: No ofrecer ayuda sin comprensión clara

### 9. Otro Contenido (86-96 líneas)
- **Criterios de evaluación**: 90%+ confianza para actuar
- **Protocolos diferenciados**: Para contenido claro vs. no claro

## Características Principales

### Enfoque Directo
- **Eliminación de metafrases**: No "déjame ayudarte" o "puedo ver que"
- **Respuestas inmediatas**: Sin introducciones innecesarias
- **Código primero**: En problemas técnicos
- **Información directa**: Sin rodeos

### Especificidad Extrema
- **Comentarios obligatorios**: Cada línea de código comentada
- **Instrucciones granulares**: Para navegación de UI
- **Suposiciones específicas**: Una sola suposición enfocada
- **Detalles completos**: Sin omisiones importantes

### Restricciones Estrictas
- **Sin resúmenes automáticos**: Solo cuando se solicite
- **Sin consejos no solicitados**: Sin pedido específico
- **Sin referencias a imágenes**: Solo "la pantalla"
- **Umbral de confianza**: 90%+ para actuar

### Formato Riguroso
- **Markdown obligatorio**: En todas las respuestas
- **LaTeX para matemáticas**: $...$ y $$...$$
- **Estructura estándar**: Para cada tipo de problema
- **Consistencia**: Formato uniforme

## Fortalezas del Prompt

### 1. Eficiencia
- **Respuestas directas**: Sin introducciones innecesarias
- **Información inmediatamente útil**: Se puede aplicar de inmediato
- **Eliminación de redundancias**: Sin metafrases o rodeos
- **Enfoque específico**: Dirigido al problema específico

### 2. Precisión Técnica
- **Código funcional**: Con comentarios completos
- **Matemáticas en LaTeX**: Formato profesional
- **Análisis comprehensivo**: Explicaciones detalladas
- **Verificación**: Doble verificación en matemáticas

### 3. Claridad
- **Instrucciones no ambiguas**: Comandos claros y precisos
- **Estructura lógica**: Flujo natural de información
- **Formato consistente**: Presentación uniforme
- **Lenguaje directo**: Sin ambigüedades

### 4. Profesionalismo
- **Tono apropiado**: Respetuoso y profesional
- **Calidad consistente**: Nivel estable
- **Métodos probados**: Enfoques establecidos
- **Fuentes confiables**: Información de calidad

## Áreas de Especialización

### 1. Problemas Técnicos
- **Programación**: Código con comentarios completos
- **Algoritmos**: Análisis de complejidad
- **Debugging**: Identificación y solución de problemas
- **Conceptos técnicos**: Explicaciones detalladas

### 2. Matemáticas
- **Cálculos**: Paso a paso con LaTeX
- **Verificación**: Doble verificación de resultados
- **Teoría**: Conceptos y fórmulas explicados
- **Precisión**: Cálculos exactos y verificados

### 3. Navegación de UI
- **Instrucciones granulares**: Cada paso específico
- **Elementos detallados**: Nombres, ubicaciones, identificadores
- **Resultados esperados**: Qué debe suceder
- **Comprehensividad**: Para usuarios no familiarizados

### 4. Comunicación
- **Emails**: Formato profesional
- **Mensajes**: Tono apropiado
- **Respuestas**: Directas y útiles
- **Estructura**: Clara y organizada

## Limitaciones y Consideraciones

### 1. Rigidez
- **Protocolos estrictos**: Poca flexibilidad
- **Formato fijo**: Estructuras obligatorias
- **Restricciones múltiples**: Muchas reglas a seguir
- **Umbral alto**: 90%+ confianza requerida

### 2. Complejidad
- **Muchas reglas**: Sistema complejo de restricciones
- **Protocolos específicos**: Para cada tipo de contenido
- **Formato riguroso**: Requiere atención a detalles
- **Estructura elaborada**: Múltiples secciones

### 3. Especialización
- **Enfoque técnico**: Prioriza problemas técnicos
- **Formato específico**: Para ciertos tipos de contenido
- **Restricciones estrictas**: Puede limitar flexibilidad
- **Umbral alto**: Puede ser demasiado restrictivo

## Comparación con Otros Prompts

### vs. Prompts Generales
- **Más específico**: Enfoque en problemas técnicos
- **Más directo**: Sin metafrases o introducciones
- **Más restrictivo**: Muchas reglas específicas
- **Más técnico**: Prioriza precisión técnica

### vs. Prompts de Desarrollo
- **Más amplio**: Cubre múltiples tipos de problemas
- **Más estructurado**: Protocolos específicos
- **Más restrictivo**: Reglas más estrictas
- **Más directo**: Respuestas inmediatas

## Recomendaciones de Uso

### Casos de Uso Ideales
- **Problemas técnicos complejos**: Programación, algoritmos
- **Matemáticas avanzadas**: Cálculos con verificación
- **Navegación de software**: Instrucciones detalladas
- **Comunicación profesional**: Emails y mensajes

### Casos de Uso Limitados
- **Conversación casual**: Demasiado formal
- **Exploración creativa**: Muy restrictivo
- **Ayuda general**: Muy especializado
- **Interacción social**: Muy técnico

## Conclusión

El system prompt de Cluely es un **instrumento altamente especializado** diseñado para **análisis y resolución de problemas técnicos** con un enfoque extremadamente directo y eficiente. Su fortaleza principal es la **precisión técnica y la eliminación de elementos innecesarios**, pero su rigidez y complejidad pueden limitar su aplicabilidad en contextos más flexibles o creativos.

El prompt es **excelente para usuarios que necesitan respuestas técnicas precisas y directas**, pero puede ser **demasiado restrictivo para interacciones más naturales o exploratorias**. Su diseño refleja una filosofía de **eficiencia máxima y precisión técnica**, priorizando la **utilidad inmediata** sobre la **flexibilidad conversacional**. 