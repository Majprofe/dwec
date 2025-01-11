# Ejercicio 1: Validación de Formulario y Eventos

## Requerimientos

Crea un formulario con los siguientes campos:

- **Identificador**: Debe estar formado por dos letras en mayúscula, un símbolo (#, $, etc.), y cuatro dígitos (ejemplo: DD#8908).
- **Nombre**: Un campo de texto de hasta 50 caracteres.
- **Correo electrónico**: Debe cumplir el formato estándar con las siguientes restricciones:
  - Letras, números, puntos, o guiones bajos/altos (máximo 20 caracteres).
  - Seguido de una arroba.
  - Nombre del dominio (máximo 20 caracteres).
  - Un punto y 2 o 3 letras.
- **Edad**: Campo numérico (mayor a 18).
- **Teléfono**: Debe cumplir con el formato internacional: un símbolo "+", seguido de 2 o 3 cifras, un guion, y 9 dígitos (ejemplo: +34-123456789).

## Lógica de Validación en JavaScript

1. **Campos requeridos**:
   - Asegúrate de que todos los campos estén completados según las reglas indicadas.
2. **Formato**:
   - Valida cada campo según el formato descrito anteriormente utilizando expresiones regulares.
3. **Mensajes de error**:
   - Muestra un mensaje de error a la derecha de los campos que no cumplen con las condiciones de validación.
   - Si un campo está vacío, muestra un mensaje distinto indicando que el campo es obligatorio.
4. **Envía los datos**:
   - Si todos los campos son válidos, simula el envío al servidor mostrando una alerta con los datos ingresados.

## Eventos

- **Evento `keydown` en el campo Identificador**:
   - Si el usuario presiona la tecla "Escape", el contenido del campo debe borrarse automáticamente.

- **Evento `mouseover` en el botón de envío**:
   - Antes de permitir que el botón sea pulsado, verifica todos los campos del formulario.
   - Si algún campo no es válido, desactiva temporalmente el botón y muestra un mensaje de advertencia.

## **EJERCICIO 2 (Consumo de API y manipulación del DOM) [6 puntos]**

Crea una aplicación que consuma la **API de Pokémon** ([PokeAPI](https://pokeapi.co/)).

### Requerimientos

1. **Formulario:**  
   - Un campo obligatorio para introducir el nombre de un Pokémon (ejemplo: `pikachu`, `charizard`).
   - Un botón para buscar.

2. **Funcionalidad:**  
   - Al hacer clic en el botón, realiza una solicitud GET a la API usando `fetch` para obtener los datos del Pokémon introducido.  
   - Si la búsqueda tiene éxito, muestra la siguiente información en pantalla:
     - **Imagen** del Pokémon.
     - **Nombre**.
     - **Altura** y **peso**.
     - **Tipos** (por ejemplo: eléctrico, fuego).  

   - Si no se encuentra el Pokémon, muestra un mensaje de error al usuario.

3. **Características adicionales:**  
   - Un botón para limpiar los resultados mostrados en pantalla.  
   - Aplica un efecto `hover` a los elementos mostrados (por ejemplo, que se resalten al pasar el ratón).

4. **Manejo de errores:**  
   - Muestra un mensaje claro si ocurre un problema en la conexión o si el nombre no existe.  

**Nota:** Utiliza estilos básicos en CSS para mejorar la presentación.
