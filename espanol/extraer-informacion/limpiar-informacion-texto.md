# 🐍 Extraer y Limpiar información de un Texto con Python

El archivo de texto originalmente era un PDF, convertido con Google Docs y descargado como archivo .txt

## Instalar Python

1. **Instalar Python** (si aún no lo tienes):

   * Descárgalo en [https://www.python.org/downloads/](https://www.python.org/downloads/)
   * Durante la instalación, marca la casilla **“Add Python to PATH”**.

2. No necesitas librerías adicionales, usaremos solo la librería estándar de Python (`re`, `io`, etc.).

---
### Crear Entorno

```bash
> conda create -n prompts python=3.11 -y

    conda create -n prompts python=3.11 -y
    3 channel Terms of Service accepted
    ....
    ....
```

## Limpiar el Texto

### Código `limpiar.py`

Guarda esto como `limpiar.py` en la misma carpeta donde tienes tu archivo `500 prompts x sector y tarea.txt`.

```python
import re

# Archivo de entrada y salida
INPUT_FILE = "500 prompts x sector y tarea.txt"
OUTPUT_FILE = "prompts_limpios.txt"

def limpiar_texto(texto):
    lineas = texto.splitlines()
    limpio = []
    skip = True  # empezamos saltando introducción/índice

    for linea in lineas:
        linea = linea.strip()

        # Saltar líneas vacías
        if not linea:
            continue

        # Detectar inicio real (cuando aparece el primer PROMPT o un encabezado claro)
        if re.match(r"PROMPT\s+\d+", linea, re.IGNORECASE):
            skip = False

        if skip:
            continue

        # Quitar números de página sueltos
        if re.fullmatch(r"\d{1,3}", linea):
            continue

        # Arreglar títulos pegados en mayúsculas
        # Ejemplo: CREACIÓNDECONTENIDOSLINKEDIN -> CREACIÓN DE CONTENIDOS LINKEDIN
        linea = re.sub(r"([A-ZÁÉÍÓÚÑ])([A-ZÁÉÍÓÚÑ])([a-záéíóúñ])", r"\1 \2\3", linea)

        # Arreglar casos de palabras pegadas (ejemplo: MarketingyAutomatización -> Marketing y Automatización)
        linea = re.sub(r"([a-záéíóúñ])([A-ZÁÉÍÓÚÑ])", r"\1 \2", linea)

        limpio.append(linea)

    return "\n".join(limpio)

def main():
    with open(INPUT_FILE, "r", encoding="utf-8") as f:
        texto = f.read()

    texto_limpio = limpiar_texto(texto)

    with open(OUTPUT_FILE, "w", encoding="utf-8") as f:
        f.write(texto_limpio)

    print(f"✅ Archivo limpio generado: {OUTPUT_FILE}")

if __name__ == "__main__":
    main()
```

---

## Usarlo

1. Abre una terminal en la carpeta donde tengas `limpiar.py` y el archivo `.txt`.

2. Ejecuta:

   ```bash
   python limpiar.py
   ```

3. Obtendrás un archivo nuevo:

   ```
   prompts_limpios.txt
   ```
#### Resultado: 

```bash
    (prompts) C:\Users\USER\OneDrive\Documentos>cd a-prompt-revision

    (prompts) C:\Users\USER\OneDrive\Documentos\a-prompt-revision>python limpiar.py
    ✅ Archivo limpio generado: prompts_limpios.txt

    (prompts) C:\Users\USER\OneDrive\Documentos\a-prompt-revision>
```

Con ese archivo limpio, ya podemos pasar a la **extracción a JSON** sin que se nos cuelen los encabezados promocionales, números de página, ni títulos pegados. 🎯



## Crear Script `extraer_json.py`

* Lee el archivo `prompts_limpios.txt`.
* Detecta sectores, tareas y subtareas.
* Divide los bloques `PROMPT n`.
* Reconoce `(Continuación del anterior)` para crear cadenas.
* Extrae placeholders `[ ... ]`.
* Genera:

  * `*_prompts.json` (uno por cada sector).
  * `catalogo.json` (con todos los sectores juntos como objeto).


Guardar **`extraer_json.py`** en la misma carpeta donde tengas `prompts_limpios.txt`:

```python
import re
import json
from pathlib import Path

INPUT_FILE = "prompts_limpios.txt"

# Sectores esperados en el documento
SECTORES = [
    "Marketing y Publicidad",
    "Ventas",
    "RRSS y Contenidos",
    "Negocios y Finanzas",
    "Tech y Programación",
    "Análisis de Datos",
    "Salud",
    "Educación",
    "Legal",
    "Esquemas de Prompts"
]

def leer_archivo():
    with open(INPUT_FILE, "r", encoding="utf-8") as f:
        return f.read()

def procesar(texto):
    lineas = texto.splitlines()
    catalogo = {s: [] for s in SECTORES}

    sector_actual = None
    tarea_actual = None
    parent_id = None
    chains = {}

    for linea in lineas:
        # Detectar sector
        if linea.strip() in SECTORES:
            sector_actual = linea.strip()
            tarea_actual = None
            continue

        # Detectar subtareas (en mayúsculas)
        if re.match(r"^[A-ZÁÉÍÓÚÑ ]{5,}$", linea.strip()):
            tarea_actual = linea.strip()
            continue

        # Detectar prompt
        match = re.match(r"PROMPT\s+(\d+)(.*)", linea.strip(), re.IGNORECASE)
        if match:
            prompt_id = match.group(1)
            resto = match.group(2).strip()

            # Continuación
            is_continuation = "(Continuación del anterior" in resto

            # Limpiar texto
            prompt_text = re.sub(r"\(Continuación del anterior\)", "", resto, flags=re.IGNORECASE).strip()

            # Placeholder
            variables = re.findall(r"\[.*?\]", prompt_text)

            # Rol
            rol = prompt_text.split(".")[0] if prompt_text.startswith("Actúa") else None

            # Cadena
            if not is_continuation:
                parent_id = prompt_id
                chains[parent_id] = 1
                paso = 1
            else:
                chains[parent_id] += 1
                paso = chains[parent_id]

            prompt = {
                "sector": sector_actual,
                "tarea": tarea_actual,
                "tarea_especifica": tarea_actual,
                "rol_persona": rol,
                "tecnica_avanzada": None,
                "variables": variables,
                "tipo_prompt": "seguimiento" if is_continuation else "base",
                "parent_id": parent_id if is_continuation else None,
                "paso_en_cadena": paso,
                "prompt_id_pdf": prompt_id,
                "prompt_texto": prompt_text,
                "fuente": INPUT_FILE
            }

            if sector_actual:
                catalogo[sector_actual].append(prompt)

    return catalogo

def guardar_json(catalogo):
    Path("json_output").mkdir(exist_ok=True)

    # Un archivo por sector
    for sector, prompts in catalogo.items():
        nombre = sector.lower().replace(" ", "_").replace("ó", "o").replace("í", "i").replace("ú", "u").replace("ñ", "n")
        archivo = Path("json_output") / f"{nombre}_prompts.json"
        with open(archivo, "w", encoding="utf-8") as f:
            json.dump(prompts, f, indent=2, ensure_ascii=False)

    # Catálogo completo
    with open("json_output/catalogo.json", "w", encoding="utf-8") as f:
        json.dump(catalogo, f, indent=2, ensure_ascii=False)

def main():
    texto = leer_archivo()
    catalogo = procesar(texto)
    guardar_json(catalogo)
    print("✅ Archivos generados en carpeta json_output/")

if __name__ == "__main__":
    main()
```


## Cómo usarlo

1. Asegúrate de tener tu entorno activo:

    ```bash
    >conda activate prompts

    (prompts) C:\Users\USER>
    ```

2. Ejecuta el script:

   ```bash
   python extraer_json.py
   ```

3. Se creará una carpeta `json_output/` con:

   * `marketing_y_publicidad_prompts.json`
   * `ventas_prompts.json`
   * … (uno por cada sector)
   * `catalogo.json`

#### Resultado: 

```bash
    (prompts) C:\Users\USER\OneDrive\Documentos\a-prompt-revision>python extraer_json.py
    ✅ Archivos generados en carpeta json_output/

    (prompts) C:\Users\USER\OneDrive\Documentos\a-prompt-revision>
```