
# Guía de Integración ChatGPT + Google Sheets

*Creado el* **2025-09-15**

---

## Visión General

**Propósito / Descripción:**
Explica cómo conectar **ChatGPT** con **Google Sheets** para automatizar tareas, generar contenido estructurado y crear datasets de manera rápida.
Incluye dos métodos: **extensión de terceros** y **Apps Script con tu propia API Key**.

**Casos de Uso Recomendados:**

* Docentes, creadores de contenido y profesionales que quieran producir ejemplos, listas o tablas sin salir de Sheets.
* Personas que aprenden **prompt engineering** y desean experimentar con flujos prácticos.

**Compatibilidad:**

* Modelos soportados: **GPT-4o, GPT-4o-mini, GPT-4.1**.
* Funciona en Google Sheets mediante **add-on** o **Apps Script**.

---

## Flujo de Trabajo Ejemplo

1. Elige tu método de conexión:

   * **Extensión (rápido, sin código)**
   * **Apps Script (más seguro, con tu API Key personal)**

2. Prepara la hoja:

   * Columna A: lista de hacks o temas.
   * Columnas B, C, D…: fórmulas que llamen a GPT para generar ejemplos, pasos de IA y prompts finales.

3. Copia la primera fórmula → arrastra hacia abajo para generar dataset completo.

4. Exporta los resultados a **Google Docs** o **Canva** para dar formato y publicar.

---

## Opciones de Conexión

### Opción 1 - Extensión de terceros

* Instalar: [GPT for Sheets and Docs](https://workspace.google.com/marketplace/app/gpt_for_sheets_and_docs/677318054654).
* Configurar tu API Key: **Extensiones → GPT for Sheets and Docs → Set API Key**.
* Funciones disponibles:

  * `=GPT("...")` → devuelve un texto.
  * `=GPT_LIST("...")` → lista expandida.
  * `=GPT_TABLE("...")` → tabla con varias columnas/filas.

---

### Opción 2 - Integración directa con Apps Script

1. Abrir **Extensiones → App Script**.
2. Guardar tu API Key en **Propiedades de Secuencia de Comandos** con el nombre `OPENAI_API_KEY`.
3. Agregar la función:

```javascript
function GPT(prompt) {
  var apiKey = PropertiesService.getScriptProperties().getProperty("OPENAI_API_KEY");
  var url = "https://api.openai.com/v1/chat/completions";
  var payload = {
    "model": "gpt-4o-mini",
    "messages": [{"role": "user", "content": prompt}],
    "max_tokens": 500
  };
  var options = {
    "method": "post",
    "headers": {
      "Authorization": "Bearer " + apiKey,
      "Content-Type": "application/json"
    },
    "payload": JSON.stringify(payload)
  };
  var response = UrlFetchApp.fetch(url, options);
  var json = JSON.parse(response.getContentText());
  return json.choices[0].message.content.trim();
}
```

4. Probar en la hoja:

```excel
=GPT("Escríbeme un chiste corto sobre programadores")
```

---

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

