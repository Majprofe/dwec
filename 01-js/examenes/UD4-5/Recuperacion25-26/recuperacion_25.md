# EXAMEN DE RECUPERACIÓN - DESARROLLO WEB EN ENTORNO CLIENTE
---

## Ejercicio 1: Formulario "Logística y Envíos"
**Objetivo**: Crear el formulario de control para una empresa de paquetería, asegurando que los códigos de seguimiento y direcciones cumplen estándares estrictos.

### Campos del formulario:
1.  **Código de Seguimiento (Tracking ID)**:
    * Formato: **2 letras (ES)**, seguidas de **9 dígitos**, y terminando en **2 letras (cualquiera)**.
    * Ejemplo válido: `ES123456789PL`, `ES000000001XY`.
    * Ejemplo NO válido: `EN123456789PL` (debe empezar por ES), `ES12345PL` (faltan números).
    * **Obligatorio**.
2.  **Código Postal de Destino**:
    * Debe ser un número de **5 dígitos**. El primero debe estar entre 0 y 5 (España).
    * Se validará con Expresión Regular (`pattern`). **Obligatorio**.
3.  **Peso del Paquete (kg)**:
    * Número con decimales. Mínimo **0.1** y Máximo **50**.
    * **Obligatorio**.
4.  **Servicio**:
    * Debe elegir entre estas opciones (no puede ser un select): "Urgente 24h", "Estándar 48h", "Económico 72h".

### Requisitos de Validación:
* **Mensajes JS**:
    * Campo vacío: *"Este campo es obligatorio"*
    * Expresión incorrecta: *"Formato incorrecto"*

### Eventos:
1.  **Lógica Focus/Blur (en "Código de Seguimiento")**:
    * **Evento `focus`**: Al hacer clic dentro del input:
        * Si había algún icono de validación (✅ o ❌), debe desaparecer.
        * Debe aparecer un texto de ayuda debajo: *"Formato requerido: AA000000000BB"*.
    * **Evento `blur`**: Al salir del input:
        * El texto de ayuda debe desaparecer.
        * **Validar el formato (Regex) en ese instante**:
            * **Si es válido**: Mostrar un icono de check (✅) al lado.
            * **Si es inválido**: Mostrar un icono de error (❌) al lado.

2.  **Lógica de Aviso (en "Peso")**:
    * **Evento `input`**: Al escribir en el campo de peso:
        * Comprobar en tiempo real el valor introducido.
        * **Si supera los 20kg**: Debe aparecer un mensaje en texto debajo del input que diga: *"¡Atención! Se aplicará recargo por sobrepeso."*
        * **Si es 20kg o menos**: El mensaje debe desaparecer.

**(4 puntos)**

---

## Ejercicio 2: Catálogo de Productos (API DummyJSON)
**Objetivo**: Consumir una API de productos paginada mediante `limit` y `skip`, e implementar una funcionalidad de "Selección de compra".

### Documentación API:
* **Endpoint**: `https://dummyjson.com/products`
* **Paginación**: Esta API no usa "página", usa `limit` (cuántos traer) y `skip` (cuántos saltar).
    * Traer los 10 primeros: `?limit=10&skip=0`
    * Traer los 10 siguientes: `?limit=10&skip=10`
    * Traer los siguientes: `?limit=10&skip=20`
* **Respuesta**:
    ```json
    {
      "products": [ ... ],
      "total": 100,
      "skip": 0,
      "limit": 10
    }
    ```

### Requisitos Funcionales:

1.  **Carga y Navegación (Reto: Cálculo del Skip)**:
    * Mostrar **10 productos** por vista.
    * Botones: **< Anteriores** y **Siguientes >**.
    * Debes manejar una variable en tu código (ej: `skipActual`) que empiece en 0.
    * Al pulsar "Siguiente", sumas 10 a esa variable y vuelves a pedir a la API.
    * Al pulsar "Anterior", restas 10 (controlando no bajar de 0).

2.  **Visualización**:
    * Renderizar una tarjeta por producto con:
        * Imagen (`thumbnail`).
        * Título (`title`).
        * Precio (`price` + "€").
        * Categoría (`category`).

3.  **Funcionalidad "Carrito Visual" (Evento Click)**:
    * **Evento**: Al hacer click en un producto.
    * **Efecto Visual**:
        * El borde de la tarjeta cambia a **Dorado (`gold`)** y grueso (4px).
        * La opacidad de la imagen baja un poco (0.8) para indicar que está "cogido".
    * **Contador**:
        * Debe haber un contador en la parte superior: *"Productos seleccionados: 0"*.
        * Cada vez que selecciono uno, el contador sube.
        * Si vuelvo a hacer click en uno seleccionado, se deselecciona (vuelve al estilo original) y el contador baja.

4.  **Buscador por Precio Máximo**:
    * Input tipo número: *"Presupuesto Máximo"*.
    * Al cambiar el valor (`input`), ocultar de la lista actual los productos que sean más caros que ese valor.

**(6 puntos)**

---

## Criterios de corrección

### Ejercicio 1 (Formulario)
* **1.0 pto** – Expresiones regulares correctas.
* **1.5 ptos** – Validación JS: Validación de cada uno de los campos, prevención del envío y mensajes inyectados en el DOM.
* **0.75 ptos** – Eventos focus/blur.
* **0.75 pto** – Evento de aviso de sobrepeso (>20kg) en tiempo real.

### Ejercicio 2 (API Tienda)
* **1.5 ptos** – Fetch inicial correcto (mostrando imagen, precio, título).
* **2.0 ptos** – **Paginación Skip/Limit**: Lógica correcta de sumar/restar al offset `skip` para navegar por los productos.
* **1.5 ptos** – **Lógica Carrito**: Evento click que modifica estilos (toggle) y actualiza correctamente una variable contadora visible en el DOM.
* **1.0 pto** – Filtro numérico local (precio máximo).

```
<form id="shippingForm">
    <!-- 1. Código de Seguimiento -->
    <div class="form-group">
        <label for="trackingId">Código de Seguimiento (Tracking ID):</label>
        <div class="input-wrapper">
            <input type="text" id="trackingId" name="trackingId" >
            <span id="trackingIcon"></span>
        </div>
    </div>

    <!-- 2. Código Postal de Destino -->
    <div class="form-group">
        <label for="postalCode">Código Postal de Destino:</label>
        <input type="text" id="postalCode" name="postalCode" title="Debe ser un número de 5 dígitos empezando por 0-5">
    </div>

    <!-- 3. Peso del Paquete -->
    <div class="form-group">
        <label for="weight">Peso del Paquete (kg):</label>
        <input type="number" id="weight" name="weight">
    </div>

    <!-- 4. Servicio -->
    <div class="form-group">
        <label for="service">Servicio:</label>
        <input type="text" id="service" name="service">
    </div>

    <button type="submit">Enviar</button>
</form>
```