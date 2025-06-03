# Prueba Técnica – “Mini Blog” en Vue 3

---

## 1. Objetivo

Construir un prototipo de **blog mínimo** usando **Vue 3**, que demuestre tu dominio de:

* **Vue Router** (rutas básicas y con parámetros dinámicos)  
* **Axios** (peticiones **GET** y **POST**)  
* Comunicación entre componentes mediante **props** y **emits**  

---

## 2. API de referencia

Utiliza **JSONPlaceholder** – un servicio público de pruebas:

* **GET** `https://jsonplaceholder.typicode.com/posts`
* **GET** `https://jsonplaceholder.typicode.com/posts/{id}`
* **POST** `https://jsonplaceholder.typicode.com/posts`

No requiere autenticación ni configuración adicional de CORS.

---

## 3. Requisitos funcionales

### 3.1 Rutas

| Ruta                | Componente           | Descripción                                                             |
|---------------------|----------------------|-------------------------------------------------------------------------|
| `/`                 | `HomeView`           | Portada con breve bienvenida.                                           |
| `/posts`            | `PostsList`          | Lista de las **10** primeras entradas devueltas por la API.             |
| `/posts/:id`        | `PostDetail`         | Detalle de la entrada seleccionada. El `id` llega a la vista como **parámetro dinámico**. |
| `/new-post`         | `NewPost`            | Formulario para crear una nueva entrada (título + cuerpo).              |

> Asegúrate de declarar `props: true` en la ruta dinámica para inyectar el parámetro `id`.

### 3.2 Listado de posts (`GET`)

* Al montar `PostsList.vue` realiza un **GET /posts**.  
* Muestra **título** y **usuario** (campo `userId`) de las primeras 10 entradas.  
* Cada elemento se renderiza mediante un componente hijo **`PostCard.vue`** que recibe la entrada por **props** y emite un evento `selected` al hacer clic.

### 3.3 Navegación hacia el detalle

* Al recibir el evento `selected`, `PostsList` debe navegar con `router.push('/posts/' + id)`.  
* `PostDetail.vue` consume **GET /posts/:id** y muestra `title` y `body`.  
* Incluye un botón **«Volver»** que retorne a `/posts` sin recargar la página.

### 3.4 Creación de post (`POST`)

* `NewPost.vue` contiene un formulario controlado para `title` y `body`.  
* Al enviar:  
  1. Ejecuta **POST /posts** con los datos.  
  2. Muestra una alerta/success toast con el **id** devuelto.  
  3. Redirige al listado (`/posts`) y refresca la lista local añadiendo el nuevo post en primera posición.

