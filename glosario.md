# Glosario profesional — Prompting y LLMs

Este glosario presenta definiciones técnicas y prácticas sobre términos y técnicas clave en prompting y modelos de lenguaje. Está pensado para profesionales y personas que comienzan en el área: definiciones precisas, ejemplos de uso y notas de aplicación.

---

## L

### LLM (Large Language Model)
Modelo de lenguaje a gran escala entrenado para predecir y generar texto. Los LLM aprenden patrones estadísticos del lenguaje a partir de grandes corpus y, con técnicas de fine-tuning o in-context learning, pueden adaptarse a tareas concretas (generación, clasificación, resumen, traducción, etc.).

Aplicaciones comunes: generación de contenido, asistentes conversacionales, soporte técnico automatizado, ayuda en programación y análisis de texto.

Consideraciones: riesgo de alucinaciones (información fabricada), sensibilidad a la redacción del prompt y limitaciones en conocimientos posteriores a su entrenamiento.

---

## P

### Prompt
Entrada textual que guía el comportamiento del modelo. Un prompt efectivo define: objetivo, contexto, formato de salida y restricciones.

Ejemplo breve:
"Resume este documento en tres puntos clave, cita las fuentes y proporciona referencias numeradas."

### Prompt engineering (Ingeniería de prompts)
Disciplina que diseña y optimiza prompts para obtener respuestas más precisas, seguras y útiles. Incluye técnicas como few-shot, chain-of-thought, RAG, y control de temperatura.

Buenas prácticas: especificar formato de salida, ofrecer ejemplos, definir el rol del modelo y limitar el alcance cuando sea necesario.

---

## F

### Few-shot learning
Estrategia que muestra al modelo varios ejemplos de entrada-salida en el propio prompt para indicar el formato, estilo y criterio de evaluación.

Patrón típico:
Instrucción general
Ejemplo 1: Input → Output
Ejemplo 2: Input → Output
Consulta: Input → Output esperado

Uso recomendado: tareas con formatos concretos (tablas, JSON, clasificación) donde no es posible o deseable reentrenar el modelo.

---

## C

### Contextualización
Proveer contexto o asignar un rol al modelo para orientar su perspectiva. Puede incluir antecedentes, restricciones y supuestos.

Ejemplo: "Eres un analista de datos; responde con un resumen técnico de máximo 150 palabras y lista supuestos." 

---

## T

### ToT (Tree of Thoughts — Árbol de pensamientos)
Marco para razonamiento que genera y evalúa múltiples cadenas de pensamiento (ramas) antes de seleccionar la solución más robusta. Es útil en problemas de búsqueda, resolución de acertijos y planificación compleja.

Fases: generar candidatos, evaluar con criterios explícitos, podar candidatos débiles y seleccionar la mejor solución.

Limitaciones: coste computacional y necesidad de criterios de evaluación claros para evitar sesgos en la selección.


### Temperatura
Parámetro de muestreo que controla la entropía del proceso generativo. Valores bajos favorecen respuestas determinísticas; valores altos introducen variabilidad.

Orientación práctica:
- 0 — Máxima determinismo (uso en código, cálculos, respuestas factuales)
- 0.2–0.4 — Respuestas técnicas y resúmenes
- 0.5–0.7 — Contenido conversacional y creativo moderado
- 0.8+ — Exploración creativa y brainstorming

Nota: la temperatura no altera el conocimiento del modelo; solo cambia la diversidad de las salidas.

---

## S

### Self-Consistency (Autoconsistencia)
Técnica que genera múltiples respuestas independientes y selecciona la más frecuente o consistente según criterios de evaluación. Mejora la robustez en razonamientos complejos y reduce errores aleatorios.

Recomendación: combinar self-consistency con prompts de evaluación explícita y métricas de verificación.

---

## R

### RAG (Retrieval-Augmented Generation — Generación aumentada por recuperación)
Arquitectura que combina recuperación de documentos relevantes con un modelo generativo. El flujo típico es: recuperar pasajes relevantes, construir un prompt con esos pasajes y generar una respuesta condicionada en la información recuperada.

Estructura recomendada del prompt RAG:
- Sección de contexto (fragmentos o extractos recuperados)
- Instrucciones claras (qué hacer con la información)
- Pregunta concreta

Precauciones: incluir metadatos sobre la fuente, evitar mezclar información conflictiva y validar con verificadores externos cuando la precisión sea crítica.

---

## I

### Instrucciones explícitas
Comandos directos que especifican la acción esperada, el formato y las restricciones. Usar verbo en imperativo, límites claros y ejemplos si aplica.

Ejemplo: "Lista en viñetas cinco riesgos de privacidad relacionados con el uso de LLM, cada uno en máximo 20 palabras."

---

## E

### Especificación de formato
Indicar de forma explícita la estructura de salida (JSON, CSV, tabla, viñetas, etc.). Facilita el procesamiento automático y reduce ambigüedad.

Ejemplo: "Devuelve JSON con claves: resumen, acciones_recomendadas, referencias (lista)."

---

## L

### Limitación de alcance
Restringir longitud, profundidad o dominio de la respuesta para mejorar precisión y relevancia.

Ejemplo: "Resume en 100 palabras y limita la respuesta a impactos económicos directos." 

---

### Notas finales
- Cross-references: combina técnicas (p. ej., RAG + few-shot) para tareas que requieren evidencia y formato estricto.
- Seguridad: cuando trabajes con información sensible, añade instrucciones para omitir, anonimizar o rechazar peticiones peligrosas.
- Experimentación: registra versiones del prompt y métricas de salida para iterar y mejorar reproducibilidad.
