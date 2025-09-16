# Generar lista de hacks para GPT + Google Sheets

*Creado el* **2025-09-15**

Ver la [Guía de Integración ChatGPT + Google Sheets](./chat-gpt--google-docs.md)

## PROMPTS

### Prompt 1 - Generar Temas (Columna A)

```markdown
Dame 20 hacks que las personas puedan implementar de inmediato usando GPT Plus y Google Sheets para automatizar tareas en menos de 15 minutos. Devuelve solo los nombres de los hacks en una lista simple.
```

### Prompt 2 - Ejemplo Práctico (Columna C)

```markdown
Explica cómo implementar este hack en menos de 15 minutos y con un coste mínimo: [HACK_NAME].
- Máximo 4 pasos.
- Sin títulos ni subtítulos.
- Respuesta concisa, menos de 80 palabras.
```

### Prompt 3 - Acciones de la IA (Columna D)

```markdown
De los pasos listados, selecciona SOLO los que debe ejecutar específicamente el asistente de IA. Devuelve la lista en viñetas.
```

### Prompt 4 - Prompt Final para el Usuario (Columna E)

````markdown
A partir de las acciones de la IA, genera el prompt exacto que el usuario debe copiar y pegar en ChatGPT.  

IMPORTANTE:
- Devuelve SOLO el prompt.  
- Ponlo dentro de un bloque de código markdown (```markdown … ```).
- No incluyas explicaciones ni texto adicional.
````

---

## Sugerencias

1. Usa restricciones de estilo (“máx. 4 pasos”, “máx. 80 palabras”) para evitar respuestas largas.
2. Empieza con una fila, valida el resultado y luego arrastra hacia abajo.
3. Exporta tu dataset a **Google Docs** o **Canva** para crear materiales visuales más atractivos.

---

# README - Proyecto: ChatGPT + Google Sheets

**Descripción:**
Este proyecto documenta cómo integrar **ChatGPT** en **Google Sheets** para crear datasets de manera automática. El flujo permite generar hacks, ejemplos, pasos de IA y prompts finales reutilizables.

**Estado:**
*Work in Progress | 2025-09-15*

**Tecnologías:**

* Google Sheets
* Google Apps Script
* OpenAI API (modelos GPT-4o y GPT-4o-mini)
* Extensión: GPT for Sheets and Docs (opcional)

**Limitaciones:**

* Las respuestas dependen de los límites de tokens de la API.
* Usar siempre con prompts restringidos para evitar verbosidad.
* Si se comparte la hoja con editores, no exponer la API Key en el código → usar propiedades de script.

**Ejemplo de Uso:**

1. Colocar lista de temas en Columna A.
2. Generar ejemplos prácticos en Columna C con `=GPT(...)`.
3. Extraer pasos de IA en Columna D.
4. Obtener el prompt final en Columna E.
5. Exportar la tabla completa para publicación.

**Formato:**
Markdown limpio, apto para GitHub o documentación interna.

---

👉 ¿Quieres que también te prepare un **ejemplo de dataset inicial en CSV** (con las 20 filas de hacks y fórmulas listas) para que lo cargues directo en Google Sheets y empieces sin copiar/pegar manualmente?

## PROMPTS

```md
Dame 20 hacks que las personas puedan implementar de inmediato usando GPT Plus y Google Sheets para automatizar tareas en menos de 15 minutos.

Requisitos:
- Devuelve solo los nombres de los hacks en lista simple, una línea por hack.
- Sin introducciones ni cierres.
- Evita relleno y palabras vacías.
```

### Ejemplo práctico conciso del hack (<15 min)

```md
Explica cómo implementar este hack en menos de 15 minutos y con coste mínimo: [HACK_NAME].

Requisitos:
- Máximo 4 pasos, 1 línea por paso.
- Menos de 80 palabras en total.
- Estilo directo/telegráfico, sin palabras vacías.
- No uses títulos ni subtítulos.
```

### Extraer acciones específicas del asistente de IA

```md
A partir de esta lista de pasos: [PASOS_GENERADOS], devuelve SOLO las acciones que debe ejecutar específicamente el asistente de IA.

Requisitos:
- Formato: viñetas cortas, una por línea.
- Sin explicaciones, sin prefacios ni cierres.
- Máximo 6 viñetas.
- Estilo conciso, sin palabras vacías.
```

### Prompt final listo para el usuario (con ejemplo de formato)

````md
A partir de estas acciones del asistente de IA: [ACCIONES_IA], genera el prompt exacto que el usuario debe copiar y pegar en ChatGPT.

Requisitos:
- Devuelve SOLO el prompt final dentro de un bloque de código markdown.
- No incluyas explicaciones ni títulos.
- Lenguaje claro y directo, sin palabras vacías.
- Personaliza variables entre [corchetes] cuando aplique.

Ejemplo de salida (formato esperado; no lo repitas literal):

```markdown
Resume el siguiente texto en un máximo de 5 puntos clave, usando frases simples y claras:

[pega aquí el texto]
```
````
