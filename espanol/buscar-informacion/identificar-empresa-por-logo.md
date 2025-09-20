# Identificar empresa y buscar página web a partir de un logo

## Descripción

Este prompt permite identificar la empresa a partir de un logo o imagen con branding y encontrar su sitio web oficial. Incluye variaciones con diferentes niveles de detalle y robustez para adaptarse a distintos casos de uso (rápido, con rol y pasos, o con formato estandarizado).

---

## Prompts

### 🔹 Versión simple

**Caso de uso:** cuando necesitas rapidez y un resultado directo.

```md
Adjunto una imagen con un logo. Por favor identifícame la empresa correspondiente y busca su sitio web oficial. Dame la URL principal, el nombre exacto de la empresa, país de origen (si lo sabes), y verifica que la página sea auténtica.
```
---

### 🔹 Versión con rol + pasos

**Caso de uso:** útil si la marca puede ser confusa o tiene muchas variantes.

```md
Actúa como un investigador experto en marcas.

Paso 1: analiza la imagen que te envío con el logo y determina con la mayor certeza posible el nombre de la empresa.  
Paso 2: busca su sitio web oficial y proporciónamelo junto con el país de origen y una breve explicación de por qué crees que esa es la empresa correcta (por ejemplo, coincidencias de imagen corporativa, colores, tipografía, referencias externas).  

Asegúrate de usar fuentes confiables.
```

---

### 🔹 Versión robusta con formato estándar

**Caso de uso:** ideal para reportes, documentación o cuando quieras mostrar metodología clara a reclutadores.

```md
Hola, te envío un logo. Quisiera que:  
1. Identifiques la empresa vinculada al logo.  
2. Confirmes que existe un sitio web oficial.  
3. Me lo des en este formato:  
   • Nombre de la empresa: …  
   • País o ciudad de origen (si lo sabes): …  
   • URL del sitio oficial: …  
   • Evidencias que lo vinculan al logo (colores, símbolos, imagen vista en la web, etc.).  

Si hay más de una posibilidad, dame una lista con probabilidades o grado de certeza.
```