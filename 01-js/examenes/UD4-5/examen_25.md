# EXAMEN DESARROLLO WEB EN ENTORNO CLIENTE
### TEMAS 4-5

---

## Ejercicio 1: Formulario "Alta de Activos Tecnológicos"

### Campos del formulario:
1.  **Número de Serie**:
    * Formato obligatorio: **3 letras mayúsculas**, seguidas de un **punto (.)**, **4 números** y finalizando con **una letra mayúscula**.
    * Ejemplo válido: `CPU.2024X`, `MON.0099A`.
    * Ejemplo NO válido: `cpu.2024x`, `A.123B`, `CPU-2024X`.
    * **Obligatorio**.
2.  **Responsable del Activo**:
    * Nombre y apellidos. Debe tener entre 10 y 40 caracteres. **Obligatorio**.
3.  **Dirección IP Asignada**:
    * Debe cumplir el patrón de una IP v4 básica (ej: `192.168.1.1`).
    * Se validará mediante **expresión regular**. **Obligatorio**.
4.  **Fecha de Instalación**:
    * Día y mes separados por /. Debe ser una fecha válida.
    * **Obligatorio**.
5.  **Departamento**:
    * Debe ser una de estas opciones (no se permite un select): "Sistemas", "Desarrollo", "Marketing". **Obligatorio**.

### Requisitos de Validación:
**Los mensajes de error deben ser personalizados mediante JavaScript** (no los del navegador por defecto).
* **Mensajes requeridos**:
    * Si el campo está vacío: *"Este dato es necesario para el inventario."*
    * Si falla el patrón (Regex): *"El formato no es correcto. Revise la sintaxis."*
* **Visualización de errores**:
    * Si un campo es erróneo, su borde debe ponerse **rojo (2px solid)** y mostrar el mensaje de error en un elemento `<span>` situado a la derecha o debajo del input.
    * Si el campo es válido, el borde debe ponerse **verde** y el mensaje de error debe desaparecer.
* El formulario **no debe enviarse** si hay errores. Si todo está bien, mostrar un `alert()` con los datos introducidos.

### Eventos (Requisitos estrictos):
1.  **Evento en "Número de Serie"**: Al hacer clic dentro del input, debe aparecer un mensaje de ayuda (placeholder) indicando: *"Ejemplo válido: ABC.1234X"*.
2.  **Evento en "Número de Serie"**: Al salir del input, el mensaje de ayuda debe desaparecer.
3.  **Evento en "Responsable"**: Conforme el usuario escribe, el texto debe convertirse automáticamente a **MAYÚSCULAS** en tiempo real.

**(4 puntos)**

---

## Ejercicio 2: Navegador de Personajes (API Paginada)

### Documentación API:
* **Endpoint base**: `https://rickandmortyapi.com/api/character`

### Requisitos Funcionales:

1.  **Carga Inicial y Paginación**:
    * Al cargar la página, se deben mostrar los personajes de la **Página 1**.
    * La interfaz debe tener dos botones: **< Anterior** y **Siguiente >**.
    * Al hacer clic en "Siguiente", la aplicación debe hacer una nueva llamada a la API usando la URL necesaria para mostrar la información de la siguiente página.
    * Al hacer clic en "Anterior", debe llamar a la api y mostrar la información de la página previa.
    * **Control de botones**: El botón "Anterior" debe deshabilitarse (.disabled) u ocultarse si estamos en la primera página. Lo mismo para "Siguiente" si es la última.

2.  **Buscador en Página Actual**:
    * Incluye un input de texto etiquetado como: *"Filtrar en esta página"*.
    * Este buscador **NO** llama a la API. Debe filtrar los resultados que ya se estan mostrando actualmente.
    * Oculta dinámicamente las tarjetas cuyo nombre no coincida con el texto escrito.

3.  **Visualización (Cards)**:
    * Mostrar para cada personaje:
        * Imagen
        * Nombre
        * Especie
        * Estado (Status)

4.  **Evento de Estilo (Selección Interactiva)**:
    * **Prohibido aplicar estilos con CSS** para este efecto.
    * Debes añadir un evento `click` a cada tarjeta (card).
    * **Efecto**: Cuando el usuario hace clic en una tarjeta, esta debe cambiar su apariencia para indicar que está "Seleccionada".
        * El **fondo** de la tarjeta debe cambiar a color oscuro (ej. `#333`).
        * El **texto** debe cambiar a color claro (ej. `#FFF`).
    * **Toggle**: Si se vuelve a hacer clic en la misma tarjeta, debe volver a su estilo original.
    * *Nota*: Esto debe realizarse manipulando la propiedad correspondiente desde JavaScript.

**(6 puntos)**

---

## Criterios de corrección

### Ejercicio 1 (Formulario)
* **1.0 pto** – Expresiones regulares correctas.
* **1.5 ptos** – Validación JS: Validación de cada uno de los campos, prevención del envío y mensajes inyectados en el DOM.
* **1.0 pto** – Eventos en número de serie funcionando correctamente para la ayuda.
* **0.5 ptos** – Evento en responsable para transformar texto a mayúsculas.

### Ejercicio 2 (API Paginada)
* **2.0 ptos** – Fetch inicial correcto y renderizado de cards (Imagen, nombre, etc.).
* **2.0 ptos** – **Lógica de Paginación**: Los botones utilizan las URL siguiente y anterior dinámicas de la API para navegar. Control de estado de los botones (null).
* **1.0 pto** – Buscador local: Filtra correctamente los elementos del DOM o del array actual.
* **1.0 pto** – **Evento de Estilo**: Implementación del click mediante JS.

Código del formulario
```
    <form id="formulario" novalidate>
        <div>
            <label for="numeroSerie">Número de Serie:</label>
            <input type="text" id="numeroSerie" name="numeroSerie" >
            <span class="error" id="errorNumeroSerie"></span>
        </div>
        <div>
            <label for="responsable">Responsable del Activo:</label>
            <input type="text" id="responsable" name="responsable" >
            <span class="error" id="errorResponsable"></span>
        </div>
        <div>
            <label for="direccionIP">Dirección IP Asignada:</label>
            <input type="text" id="direccionIP" name="direccionIP" >
            <span class="error" id="errorDireccionIP"></span>
        </div>
        <div>
            <label for="fechaInstalacion">Fecha de Instalación:</label>
            <input type="text" id="fechaInstalacion" name="fechaInstalacion" placeholder="DD/MM" >
            <span class="error" id="errorFechaInstalacion"></span>
        </div>
        <div>
            <label for="departamento">Departamento:</label>
            <input type="text" id="departamento" name="departamento" >
            <span class="error" id="errorDepartamento"></span>
        </div>
        <button type="submit">Enviar</button>
    </form>
```