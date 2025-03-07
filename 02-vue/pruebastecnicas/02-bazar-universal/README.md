# 02 - Desarrollo Full Stack de Bazar

Debes crear una aplicación que consta de **3 componentes principales**:

- Una caja de búsqueda
- La lista de resultados
- Descripción del detalle del producto

La aplicación debe constar de servidor y cliente. El servidor debe exponer un API RESTful y el cliente consumirlo.
- Usa el archivo [products.json](./products.json) para obtener los datos de los productos y crea una API para consumirlos.

![](./images/bazar.jpg)

## Contexto

Somos un bazar con todo tipo de productos. Queremos crear nuestra app web. Por ahora **nuestro mercado va a ser el móvil**.

Esta primera versión los usuarios podrán buscar el nombre del producto, le mostraremos una lista de productos y podrán hacer clic en cada uno para ver el detalle. 

Ten en cuenta:
- No sabemos si el framework que utilicemos ahora será el definitivo, pero querremos reutilizar el máximo de código posible.

- La aplicación debe ser fácil de usar y **agradable a la vista**. No importa si copias el diseño o usas un catálogo de componentes.

- **Es MUY importante el SEO de la aplicación**. Así que el robot de Google debe poder ver bien nuestra página, navegarla sin problemas y el rendimiento debe ser el adecuado.

- Queremos también que los usuarios puedan compartir los productos en redes sociales.

## Requisitos

- La aplicación debe estar hecha con Typescript.

### Funcionalidad

1. **Crea las 3 páginas**: Inicio con caja de búsqueda, resultados de búsqueda y detalle.

2. **Las rutas de las páginas serán**:
  - Home con caja de búsqueda
    - Ruta: `/`
    - Descripción: Simplemente muestra una caja de búsqueda para poder hacer la búsqueda de productos. Al realizar la búsqueda navegar a la vista de Resultados de búsqueda.
  
  - Resultados de búsqueda:
    - Ruta: `/items?search=`, por ejemplo: `/items/?search=laptop`
    - Descripción: Muestra justo debajo de la caja de búsqueda, el número de resultados y también los resultados que muestra para cada categoría. En cada tarjeta de los resultados muestra: título, descripción, precio, categoría, imagen y puntuación.

  - Detalle de producto: "/items/:id"
    - Ruta: `/items/:id`
    - Descripción: Muestra la descripción completa del producto, incluyendo todos los detalles que tengas: precio, descripción, marca, stock, categoría, etc. Muestra todas las imágenes. También un botón para poder realizar la compra (aunque no funcione)

3. **API**: Debes crear dos endpoints, debes basarte en el contenido del archivo `products.json` que tienes en este repositorio pero no tienes por qué seguir ese esquema. Los endpoints a crear son:
  - `/api/items?q=:query` donde `:query` es la búsqueda que hace el usuario. Debe devolver un JSON con los datos a mostrar en la lista de items.
  - `/api/items/:id`, donde `:id` es el id del producto seleccionado. Debe devolver un JSON con los datos del item seleccionado.

4. **Despliegue**: La aplicación debe estar desplegada en algún servicio de hosting gratuito (Netlify, Vercel, Firebase, etc) y debe ser accesible a través de una URL pública. **Indica la URL al hacer la Pull Request.**

5. **Test**: La aplicación debe tener AL MENOS un test. Haz el test que consideres más importante para tu aplicación.

## Consejos sobre el código

1. **Estructura del código**: El código debe estar bien organizado y fácil de leer.

2. **Semántica HTML**: El HTML debe ser semántico y accesible.

3. **Pensando en equipo**: Prepara tu proyecto pensando que cualquier persona de tu equipo puede tener que trabajar en él en el futuro. (scripts en el package.json, mínima documentación en el README, comentarios en el código si es necesario, etc)

4. **Formatea tu código**: Asegúrate de que tu código está formateado de forma consistente. Puedes usar Prettier o cualquier otra herramienta que te guste.

5. **Preparado para producción**: Asegúrate de que tu aplicación está lista para producción. Minimiza el código, optimiza las imágenes, etc.

## Desafíos adicionales

**¿Quieres ir más allá?** Estos son algunos desafíos adicionales que puedes intentar:

- Implementa la funcionalidad de carrito de la compra.
- Haz que el diseño sea responsive.
- Integra la paginación tanto en la API como en la web.

## Entrevista

Si pasas a la siguiente fase, te pediremos que hagas una entrevista con nosotros. Durante la entrevista, te pediremos que expliques tu código y que hagas algunos cambios en el mismo.

- Nos tendrás que explicar el código que has escrito y las decisiones que has tomado.
- Haremos cambios en el JSON y tendrás que adaptar el código en vivo.

Buena suerte y ¡diviértete programando!

# Rúbricas de Corrección – Desarrollo Full Stack de Bazar

A continuación, se presenta la tabla con los criterios de evaluación para la prueba técnica. La puntuación total es de **10 puntos**.

| **Categoría**                           | **Descripción**                                                                                                                                                                                                                                                                                                                         | **Puntos** |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|
| **1. Búsqueda, Rutas e Integración**   | Se evalúa la implementación de la caja de búsqueda en la página de inicio, la navegación a la página de resultados mediante la query (`/items?search=`) y la ruta de detalle (`/items/:id`). También se verifica que el frontend consuma correctamente la API para mostrar la información de cada producto.                       | **2.5**    |
| **2. API y Respuesta**                 | Se espera que el servidor (en TypeScript) exponga al menos dos endpoints: `/api/items?q=:query` y `/api/items/:id`. Deben manejar el archivo `products.json` (o su equivalente) para devolver datos de búsqueda y detalle. Se valora el correcto manejo de errores (por ejemplo, producto no encontrado) y la estructura clara del JSON.  | **2**      |
| **3. Despliegue**                      | La aplicación debe estar desplegada en un servicio de hosting gratuito (Netlify, Vercel, Firebase, etc.). Se comprueba que la URL sea accesible públicamente y que se mencione en el README o Pull Request.                                                                                                                            | **0.5**    |
| **4. Calidad del Código**              | Se revisa la organización de carpetas y archivos, la legibilidad del código, el uso de TypeScript, la consistencia en la nomenclatura, los principios de DRY (Don’t Repeat Yourself), y el uso de formateadores o linters (ESLint, Prettier). También se valora la separación de responsabilidades y la facilidad de mantenimiento.       | **3**      |
| **5. Documentación (README)**          | El README debe incluir: instrucciones de instalación, ejecución y despliegue de la aplicación, así como una explicación mínima de la arquitectura o decisiones técnicas (framework elegido, etc.). Se valora la claridad y la información suficiente para que cualquier persona pueda clonar, instalar y ejecutar el proyecto.      | **1**      |
| **6. Tests**                           | Se requiere al menos **un test**. Puede ser un test unitario, de integración o E2E que valide alguna funcionalidad esencial (por ejemplo, la lógica de búsqueda o la obtención de datos correctos en `/api/items/:id`).                                                                                                                 | **1**      |

**Puntuación total: 10 puntos**
