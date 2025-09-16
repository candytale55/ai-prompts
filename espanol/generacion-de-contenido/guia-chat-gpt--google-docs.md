
# Guía de Integración ChatGPT + Google Sheets

*Creado el* **2025-09-15**


> Explica cómo conectar **ChatGPT** con **Google Sheets** para automatizar tareas, generar contenido estructurado y crear datasets de manera rápida.

Sugiere dos métodos: **extensión de terceros** y **Apps Script con tu propia API Key**.


**Compatibilidad:**

* Modelos soportados: **GPT-4o, GPT-4o-mini, GPT-4.1**.
* Funciona en Google Sheets mediante **add-on** o **Apps Script**.



## Pasos

1. Elige método de conexión:

   * **Extensión (rápido, sin código)**
   * **Apps Script (más seguro, con tu API Key personal)**

2. Prepara la hoja:

   * Columna A: lista de temas.
   * Columnas B, C, D…: fórmulas que llamen a GPT para generar ejemplos, pasos de IA y prompts finales.

3. Copia la primera fórmula → arrastra hacia abajo para generar dataset completo.

4. Exporta los resultados a **Google Docs** o **Canva** para dar formato y publicar.



## Opciones de Conexión

### Opción 1 - Extensión de terceros

* Instalar: [GPT for Sheets and Docs](https://workspace.google.com/marketplace/app/gpt_for_sheets_and_docs/677318054654) u otra extensión similar.
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
