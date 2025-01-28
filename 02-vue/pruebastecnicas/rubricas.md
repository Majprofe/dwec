# Rúbricas para Pruebas Técnicas Vue

## Funcionalidades

### Lista de Lectura

1. **Visualización de Libros Disponibles:**
   - La aplicación debe mostrar una lista de libros disponibles que el usuario pueda revisar.

2. **Creación de Lista de Lectura:**
   - El usuario debe ser capaz de crear una lista de lectura a partir de los libros disponibles.
   - En la UI debe quedar claro qué libros están en la lista de lectura y cuáles no.
   - También debe ser posible mover un libro de la lista de lectura a la lista de disponibles.

3. **Filtrado de Libros por Género y Páginas:**
   - Los usuarios deben poder filtrar la lista de libros disponibles por género y número de páginas.
   - Se debe mostrar un contador con el número de libros disponibles, el número de libros en la lista de lectura y el número de libros disponibles en el género seleccionado.

4. **Sincronización de Estado:**
   - Debe haber una sincronización del estado global que refleje el número de libros en la lista de lectura y el número de libros todavía disponibles.
   - Si un libro se mueve de la lista de disponibles a la lista de lectura, el recuento de ambos debe actualizarse en consecuencia.

5. **Persistencia de Datos:**
   - La aplicación debe persistir los datos de la lista de lectura en el almacenamiento local del navegador.
   - Al recargar la página, la lista de lectura debe mantenerse.

6. **Sincronización entre Pestañas:**
   - Si el usuario abre la aplicación en dos pestañas diferentes, los cambios realizados en una pestaña deben reflejarse en la otra.
   - Sin necesidad de usar Backend.

7. **Despliegue:**
   - La aplicación debe estar desplegada en algún servicio de hosting gratuito (Netlify, Vercel, Firebase, etc.).
   - Indica la URL en el README.

8. **Test:**
   - La aplicación debe tener al menos un test. Haz el test que consideres más importante para tu aplicación.

9. **Diseño Responsive:**
   - Haz que tu diseño sea responsive.

---

### Bazar Universal

1. **Crea las 3 Páginas:**
   - Inicio con caja de búsqueda.
   - Resultados de búsqueda.
   - Detalle del producto.

2. **Rutas de las Páginas:**
   - **Home con Caja de Búsqueda:**
     - **Ruta:** `/`
     - **Descripción:** Simplemente muestra una caja de búsqueda para buscar productos. Al realizar la búsqueda, navegar a la vista de Resultados de Búsqueda.
   - **Resultados de Búsqueda:**
     - **Ruta:** `/items?search=`, por ejemplo: `/items?search=laptop`.
     - **Descripción:** Muestra justo debajo de la caja de búsqueda el número de resultados y también los resultados que muestra para cada categoría. En cada tarjeta de los resultados muestra:
       - Título.
       - Descripción.
       - Precio.
       - Categoría.
       - Imagen.
       - Puntuación.
   - **Detalle de Producto:**
     - **Ruta:** `/items/:id`.
     - **Descripción:** Muestra la descripción completa del producto, incluyendo todos los detalles que tengas:
       - Precio.
       - Descripción.
       - Marca.
       - Stock.
       - Categoría.
       - Todas las imágenes.
       - Botón para realizar la compra (aunque no funcione).

3. **API:**
   - **Endpoints a Crear:**
     - `/api/items?q=:query`, donde `:query` es la búsqueda que hace el usuario. Devuelve un JSON con los datos a mostrar en la lista de items.
     - `/api/items/:id`, donde `:id` es el id del producto seleccionado. Devuelve un JSON con los datos del item seleccionado.

4. **Despliegue:**
   - La aplicación debe estar desplegada en algún servicio de hosting gratuito (Netlify, Vercel, Firebase, etc.).
   - Indica la URL al hacer la Pull Request.

5. **Test:**
   - La aplicación debe tener al menos un test. Haz el test que consideres más importante para tu aplicación.

6. **Carrito de la Compra:**
   - Implementa la funcionalidad de un carrito de la compra donde puedas añadir y eliminar elementos.

7. **Diseño Responsive:**
   - Haz que el diseño sea responsive.

---

## Aspectos Generales

### Rúbrica de Evaluación

| **Aspectos** | **4 Excelente** | **3 Satisfactorio** | **2 Mejorable** | **1 Insuficiente** |
|--------------|----------------|---------------------|-----------------|-------------------|
| **Diseño**   | Muy original y creativo tanto en la estructura de la página web como en el fondo y paleta de colores. | Página web original y creativa tanto en su estructura como en el fondo y paleta de colores. | Página web que, unas veces, mantiene una estructura coherente y otras no. El fondo y la paleta de colores es suficiente. | Página web que pocas veces mantiene la coherencia en su estructura. El fondo y la paleta cromática son inadecuados. |
| **Código**  | Realiza toda la web con componentes y utiliza adecuadamente las funcionalidades de Vue, además añade plugins adicionales de Vue. | Realiza toda la web con componentes y utiliza adecuadamente las funcionalidades Vue como router, components, etc. | Crea componentes y vistas pero no estructura bien el código y no está claro. Además mezcla conceptos o se nota que está hecho por una IA. | Crea pocos componentes y no utiliza adecuadamente la API de Vue. |
| **API**      | Crea y consume recursos de la API de forma adecuada, además la tiene desplegada. | La API funciona correctamente pero no está desplegada. | Crea la API pero no la tiene desplegada o contiene fallos. | No crea la API y consume los datos de un JSON. |

---

## Defensa de la Prueba Técnica

Se realizará una defensa de las dos pruebas técnicas. En esta defensa se realizarán preguntas para que el alumno demuestre si ha realizado las pruebas por él mismo.
