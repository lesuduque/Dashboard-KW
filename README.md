# Dashboard SPA (Single File App)

Este dashboard es una Single File App (SPA), con estas características:

- Un solo archivo `.html`
- CSS embebido
- JavaScript embebido
- Persistencia usando `localStorage` (almacenamiento en el navegador)
- Sin backend
- Sin base de datos externa

---

## Qué muestra ahora

### ✅ Keywords
Toda la data de los 6 países (**CR, HN, GT, NI, SV, PA**) con filtros por:

- País
- Producto
- Jerarquía (**H1 / H2 / H3**)
- Tipo (**informacional / transaccional**)

**Notas**
- Las métricas de arriba muestran el conteo por país.
- Al final hay un formulario para agregar nuevas keywords **sin tocar el Excel**.

---

### ✅ Banco de copys
Las **25+ entradas** del banco, filtrables por:

- Plantilla
- Elemento
- Búsqueda libre

Cada tarjeta muestra:
- Texto base
- Versión **"vos"** cuando difiere del **"tú"**
- Notas de uso

**Notas**
- Incluye formulario para agregar copys nuevos con versión **tú / vos**.

---

### ✅ Estructura
Las 5 plantillas:

- Inicio
- Sobre Mi Viaje
- Promociones
- Tutoriales
- Experiencias

Con opciones de:
- H1
- Bloques H2
- H3 opcionales
- CTA
- Texto de apoyo

**Sobre Mi Viaje**
- Incluye **5 opciones** de copy completo (**H1 + párrafos**).
- Tiene filtro para ver solo versión **"vos"** o **"tú"**.
- Muestra las **keywords foco** de cada opción.

---

## Estructura

- **Estructura:** HTML  
- **Estilos:** CSS  
- **Lógica / Interactividad:** JavaScript  
- **Datos:** JSON (embebido en JS)

---

## Funcionamiento actual

- El navegador lee el archivo
- Ejecuta el HTML + CSS + JS
- El archivo queda como “solo lectura”
- El navegador **NO** tiene permiso para:
  - modificar archivos del disco
  - sobrescribir el HTML
  - escribir dentro del `<script>`

---

## Lo que pasa ahora (almacenamiento de textos)

El almacenamiento actual funciona así:

- Los datos **NO** se guardan en el código
- Se guardan en el navegador, usando `localStorage`
- Se ve el dashboard “vivo”
- Se cierra el navegador
- Se vuelve a abrir
- Los datos siguen ahí

**En la práctica, para el uso diario:**  
Es como si los textos nuevos agregados estuvieran en el código, pero técnicamente están fuera del archivo: están guardados en el navegador.

---

## Meta

Que permita guardar y seguir creciendo un banco de texto (keywords y copys) **sin servidores** o backend complejo.

**Escenario deseado (multiusuario):**
- Persona A → agrega keyword → se guarda en la nube
- Persona B → abre la app → ve la keyword de A

---

## Opciones para pasar a multiusuario (datos en la nube)

### 1) OPCIÓN 1 — Backend con Firebase / Supabase

Un servicio que da:
- una base de datos lista
- en la nube
- sin programar servidores
- gratis al inicio
- pensado para texto
- ideal para dashboards internos

**Ventajas**
- Multiusuario
- Funciona desde cualquier navegador
- No se pierden datos
- Gratis para empezar
- No se crean nuevos archivos en el proyecto (lo que conserva la lógica Single File App)
- El HTML sigue siendo UNO solo

**Desventajas**
- Hay que agregar un poco de código nuevo

---

### 2) OPCIÓN 2 — Backend propio ultra simple (Node + JSON)

- Un mini servidor
- Un archivo `data.json`
- Guarda todo ahí

Ejemplo:
- `server.js`
- `data.json`

Cuando alguien agrega algo:
- se escribe en `data.json`

**Ventajas**
- Control total
- Los datos son literalmente un JSON

**Desventajas**
- Se necesita hosting con Node
- Alguien tiene que mantener eso
- Más frágil
- Más técnico