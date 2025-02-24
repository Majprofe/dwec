# EXAMEN DESARROLLO WEB EN ENTORNO CLIENTE  
### TEMAS 4-5

## Ejercicio 1: Formulario de Registro de Usuarios  
**Objetivo**: Crear una página para registrar usuarios con validación de formularios y eventos.

El formulario tendrá los siguientes campos:  
- **Usuario**: entre 5 y 15 caracteres alfanuméricos. Obligatorio.  
- **Correo Electrónico**:  
  - Formato válido de email (ej. usuario@dominio.com).  
  - Se validará mediante **expresión regular**. Obligatorio.  
- **Código Personal**:  
  - Debe estar compuesto por **dos letras mayúsculas, seguidas de tres o cuatro letras minúsculas y dos números**.  
  - **Ejemplo válido**: `ABcde12`, `XYabcd34`.  
  - Obligatorio.  
- **Código de Producto**:  
  - Formato `ABC-1234-XY`.  
  - **Tres letras mayúsculas** seguidas de **un guion (-)**, **cuatro números**, **otro guion (-)** y **dos letras mayúsculas**.  
  - **Ejemplo válido**: `XPT-4321-ZQ`.  
  - **Ejemplo NO válido**: `abc-1234-xy`, `A1B-123-XY`.  
  - Obligatorio.  
- **Edad**: número entre 18 y 99. Obligatorio.  
- **Provincia**: selección con tres opciones (Sevilla, Córdoba, Granada). Obligatorio.  

### Validaciones:  
- Si falta un campo obligatorio: *"Este campo es obligatorio."*  
- Si el formato no es válido: *"El valor introducido no cumple con lo pedido."*  

Cada campo incorrecto debe resaltarse con un borde rojo y mostrar el mensaje de error correspondiente.  
No se permitirá enviar el formulario hasta que todos los campos sean correctos.
Las validaciones se realizarán mediante HTML y los mensajes de error se personalizarán con Javascript

### Eventos:  
- Al **focalizar el input Código Personal**, se vaciará el campo.  
- Al **perder el foco en Código Personal**, se validará el campo y aparecerá un icono verde (✔) si es correcto o rojo (❌) si es incorrecto.  
- Al **focalizar la provincia**, se mostrará un mensaje de ayuda con las opciones disponibles. El mensaje desaparecerá al perder el foco.  
- Si todo es válido, al enviar el formulario se mostrarán los datos en un \`alert()\`.  

**(4 puntos)**  

---

## Ejercicio 2: Consumo de API de SpaceX  
**Objetivo**: Crear una aplicación que consuma la **API de SpaceX** y muestre información sobre lanzamientos o cohetes.

### Documentación:  
API oficial: [https://github.com/r-spacex/SpaceX-API](https://github.com/r-spacex/SpaceX-API)  
Endpoints útiles:  
- **Todos los lanzamientos**: `https://api.spacexdata.com/v4/launches`  
- **Información de cohetes**: `https://api.spacexdata.com/v4/rockets`  
- **Consulta de una misión por ID**: `https://api.spacexdata.com/v4/launches/{id}`  
- **Consulta de un cohete por ID**: `https://api.spacexdata.com/v4/rockets/{id}`  

### Requisitos:  
1. La aplicación tendrá un formulario con los siguientes campos:  
   - **Tipo de consulta**: "Lanzamientos" (para ver información de misiones) o "Cohetes" (para ver detalles técnicos de los cohetes). Obligatorio.  
   - **ID (opcional)**: Si se introduce, buscará un lanzamiento o cohete específico.  
   - **Búsqueda por nombre**: Un input para buscar un **cohete** o una **misión** por su nombre.  

2. **El filtro de búsqueda por nombre solo se aplicará después de obtener los datos de la API**.  
   - Se mostrará la lista completa y el usuario podrá filtrar dinámicamente los resultados al escribir en el input.  

3. Si el usuario elige "Lanzamientos", se mostrará una lista con los siguientes datos en **formato de cards**:  
   - **ID del lanzamiento** → `id`  
   - **Nombre de la misión** → `name`  
   - **Fecha de lanzamiento** → `date_utc`  
   - **Éxito o fracaso del lanzamiento** → `success`  
   - **Enlace al webcast (si existe)** → `links.webcast`  

4. Si el usuario elige "Cohetes", se mostrará una lista con los siguientes datos en **formato de cards**:  
   - **ID del cohete** → `id`  
   - **Nombre del cohete** → `name`  
   - **Descripción del cohete** → `description`  
   - **Altura del cohete (en metros)** → `height.meters`  
   - **Diámetro del cohete (en metros)** → `diameter.meters`  

5. Los datos deben mostrarse en **cards bien diseñadas**, con un estilo claro y estructurado.  

6. **Debe aplicarse efecto hover a cada card con eventos de JavaScript, no con CSS.**  

7. La interfaz debe estar bien organizada y legible.  

8. Se deben manejar errores como búsquedas inexistentes o fallos de conexión.  

**(6 puntos)**  

---

## Criterios de corrección  

✅ **Ejercicio 1:**  
✔ **1 punto** – Validación de todos los campos antes del envío.  
✔ **1.5 puntos** – Mensajes de error visibles y formulario solo se envía si es válido.  
✔ **1 punto** – Eventos correctos en los inputs (foco y validación).  
✔ **0.5 puntos** – Ayuda en el campo de selección de provincia.  

✅ **Ejercicio 2:**  
✔ **2 puntos** – Consulta correcta a la API y obtención de la información según el tipo seleccionado, teniendo en cuenta si se pasó ID o no.  
✔ **2 puntos** – Los datos se muestran en cards estructuradas y bien diseñadas.  
✔ **1 punto** – Input de búsqueda en tiempo real para filtrar cohetes o misiones por nombre después de obtener los datos.  
✔ **1 punto** – Efecto hover aplicado mediante eventos de JavaScript.  

