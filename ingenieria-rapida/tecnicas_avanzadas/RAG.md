# RAG como Técnica de Prompt Engineering 🎯

## ¿Qué es RAG en Prompting?

RAG es una técnica de prompting donde **incluyes información específica en tu prompt** para que el AI genere respuestas más precisas y verificables.

**Fórmula simple:**
```
Información relevante + Instrucciones claras + Pregunta = Respuesta fundamentada
```

## Estructura Básica

```markdown
# INFORMACIÓN BASE
[Datos, documentos o código relevante]

# INSTRUCCIONES
- Usa solo la información proporcionada
- Cita las fuentes
- Si falta info, dilo claramente

# PREGUNTA
[Tu consulta específica]
```

## 📋 Plantilla Simple

```markdown
**CONTEXTO:**
[Pega aquí la información relevante]

**ROL:** Actúa como [especialista en X]

**TAREA:** [Lo que necesitas que haga]

**RESTRICCIONES:**
- Solo usa la información del contexto
- Menciona la fuente de cada dato importante
- Di "no hay suficiente información" si es el caso

**FORMATO:** [Cómo quieres la respuesta]

**PREGUNTA:** [Tu consulta]
```

## 💡 Ejemplo Práctico

### Antes (Prompting normal):
```
"¿Cómo actualizar React Router en mi proyecto?"
```

### Después (RAG Prompting):
```
**CONTEXTO:**
- Proyecto actual usa React Router v5.3.0
- Package.json muestra dependencias: react-router-dom: "^5.3.0"
- Tenemos 15 componentes usando useHistory hook
- Documentación dice v6 cambió useHistory por useNavigate

**ROL:** Senior React Developer

**TAREA:** Crear plan de migración paso a paso

**RESTRICCIONES:**
- Usar solo info del contexto
- Citar cambios específicos mencionados

**PREGUNTA:** ¿Cómo migrar este proyecto a React Router v6?
```

## ✅ Cuándo Usar RAG Prompting

**✅ Usa RAG cuando:**
- Tienes documentación específica
- Necesitas respuestas verificables
- Trabajas con código/datos específicos
- Quieres evitar información incorrecta

**❌ No uses RAG cuando:**
- Haces preguntas generales
- Necesitas creatividad libre
- La conversación es casual

## 🎯 Beneficios Simples

1. **Más precisión**: El AI usa TUS datos, no su memoria
2. **Verificable**: Puedes comprobar de dónde sale cada respuesta
3. **Actualizado**: Funciona con info nueva que el AI no conoce
4. **Específico**: Respuestas adaptadas a tu contexto

## 🔧 Tips Rápidos

### Para mejores resultados:
- **Sé específico** en el rol ("Senior Python Developer" vs "programador")
- **Limita el contexto** (solo info relevante, no todo)
- **Pide citas** ("menciona de qué documento viene cada dato")
- **Define el formato** ("lista de pasos", "tabla comparativa", etc.)

### Errores comunes:
- Dar demasiado contexto irrelevante
- No especificar el formato de respuesta
- Olvidar pedir que cite fuentes
- No definir qué hacer si falta información

## Ejemplos y templates
1. [ir a plantilla basica](./rag/template_rag.md)
2. [ir a ejemplo1](./rag/example.md)
3. [ir a ejemplo marketing](./rag/example_marketing.md)
4. [ir a ejemplo para RH](./rag/example_rh.md)


## 🚀 Resultado

Con RAG prompting obtienes respuestas que son:
- **Precisas** (basadas en TUS datos)
- **Confiables** (puedes verificar las fuentes)
- **Útiles** (específicas para tu situación)
- **Actualizadas** (con tu información más reciente)