Este dashboard es una **Single File App (SPA)**, con estas características:


- Un solo archivo `.html`

- CSS embebido

- JavaScript embebido

- Persistencia usando **localStorage** (almacenamiento en el navegador)

- Sin backend

- Sin base de datos externa



---


## Qué muestra ahora


### ✅ Keywords

- Toda la data de los **6 países** (**CR, HN, GT, NI, SV, PA**) con filtros por:

&#x20; - país

&#x20; - producto

&#x20; - jerarquía (**H1 / H2 / H3**)

&#x20; - tipo (**informacional / transaccional**)

- Las métricas arriba muestran el **conteo por país**.

- Al final hay un **formulario** para agregar nuevas keywords **sin tocar el Excel**.


### ✅ Banco de copys

- Las **25+ entradas** del banco, filtrables por:

&#x20; - plantilla

&#x20; - elemento

&#x20; - búsqueda libre

- Cada tarjeta muestra:

&#x20; - el texto base

&#x20; - la versión **"vos"** cuando difiere del **"tú"**

&#x20; - las notas de uso

- También incluye **formulario** para agregar copys nuevos con versión **tú/vos**.



### ✅ Estructura

- Las **5 plantillas**:

&#x20; - Inicio

&#x20; - Sobre Mi Viaje

&#x20; - Promociones

&#x20; - Tutoriales

&#x20; - Experiencias

- Cada plantilla contiene:

&#x20; - opciones de **H1**

&#x20; - bloques **H2**

&#x20; - **H3** opcionales

&#x20; - **CTA**

&#x20; - texto de apoyo


**Sobre Mi Viaje**

- **5 opciones** de copy completo (**H1 + párrafos**)

- Filtro para ver solo versión **"vos"** o **"tú"**

- Incluye las **keywords foco** de cada opción

---


## Estructura



| Tipo | Lenguaje |

|------|----------|

| Estructura | HTML |

| Estilos | CSS |

| Lógica / Interactividad | JavaScript |

| Datos | JSON (embebido en JS) |



---



## Funcionamiento actual

- El navegador lee el archivo

- Ejecuta el **HTML + CSS + JS**

- El archivo queda como “solo lectura”

- El navegador **NO** tiene permiso para:

&#x20; - modificar archivos del disco

&#x20; - sobrescribir el HTML

&#x20; - escribir dentro del `<script>`



---


## Lo que pasa ahora (almacenamiento de textos)


Funciona así:


- Los datos **NO** se guardan en el código

- Se guardan en el navegador, usando **localStorage** (almacenamiento en el navegador)

- Se ve el dashboard “vivo”

- Se cierra el navegador

- Se vuelve a abrir

- Los datos siguen ahí


En la práctica, para el uso diario:  

Es como si los textos nuevos agregados estuvieran en el código, pero técnicamente están fuera del archivo: están en el navegador.


---


## Meta

Que permita guardar y seguir creciendo un banco de texto (**keywords y copys**) sin servidores o backend complejo.

- Persona A → agrega keyword → se guarda en la nube  

- Persona B → abre la app → ve la keyword de A

---


## Opciones

### 1) OPCIÓN 1 — Backend con Firebase / Supabase

Un servicio que da:

- Una base de datos lista

- En la nube

- Sin programar servidores

- Gratis al inicio

- Pensado para texto

- Ideal para dashboards internos



**Ventajas**

- Multiusuario

- Funciona desde cualquier navegador

- No se pierden datos

- Gratis para empezar

- No se crean nuevos archivos en el proyecto (lo que conserva la lógica Single File App)

- El HTML sigue siendo **UNO** solo



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

