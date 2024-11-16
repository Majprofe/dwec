
# Ejercicios de Repaso DWEC

## **Ejercicio 1: Tienda Online (30 minutos)**
**Objetivo**: Repasar sintaxis, objetos, clases y Arrays.

1. Crea un **objeto** llamado `Producto` que represente un producto de una tienda online con las propiedades:
   - `nombre` (string)
   - `precio` (número)
   - `categoria` (string)
2. Crea una **clase** `Carrito` que permita:
   - Añadir productos (un método `agregarProducto` que reciba un objeto `Producto`).
   - Mostrar todos los productos añadidos.
   - Calcular el total de los precios de los productos.

3. Crea tres productos utilizando el objeto `Producto`, añade esos productos al carrito y muestra:
   - La lista de productos añadidos.
   - El total.

---

## **Ejercicio 2: Gestión de Usuarios (25 minutos)**
**Objetivo**: Trabajar objetos nativos, Arrays, Map y Set.

1. Dado un array de objetos `usuarios` como el siguiente:

```javascript
const usuarios = [
  { nombre: "Ana", edad: 25, email: "ana@gmail.com" },
  { nombre: "Luis", edad: 32, email: "luis@gmail.com" },
  { nombre: "María", edad: 29, email: "maria@gmail.com" },
  { nombre: "Luis", edad: 32, email: "luis@gmail.com" }, // Usuario duplicado
];
```

Haz lo siguiente:
- Crea un **Set** con los correos electrónicos para eliminar duplicados.
- Transforma el array en un **Map** donde la clave sea el correo electrónico y el valor sea el objeto del usuario.
- Devuelve una lista de los usuarios ordenados alfabéticamente por nombre.

---

## **Ejercicio 3: Validación de un Formulario de Registro (30 minutos)**
**Objetivo**: Repasar validación de formularios y eventos.

1. Crea un formulario en HTML con los siguientes campos:
   - Nombre (texto)
   - Correo electrónico (texto)
   - Contraseña (texto)
   - Edad (número)
   - Número de teléfono (texto)
   - Nickname (texto)
   - Botón de enviar

2. Enlaza un archivo JavaScript que valide lo siguiente al hacer clic en el botón de enviar:
   - El nombre debe tener al menos 3 caracteres.
   - El correo electrónico debe tener un formato válido.
   - La contraseña debe tener al menos 8 caracteres.
   - La edad debe ser mayor o igual a 18.
   - El número de teléfono debe seguir el siguiente patrón (+XX-XXXXXX) X corresponde a un número.
   - El nickname debe coincidir con:
        - Las dos primeras letras del nombre
        - El sufijo del dominio del email (com o es por ejemplo)
        - Edad
        - Tercer y cuarto dígito del número de teléfono después del guión.

3. Si hay algún error, muestra un mensaje junto al campo correspondiente.

---

## **Ejercicio 4: Gestión de Ventanas del Navegador (20 minutos)**
**Objetivo**: Trabajar con el BOM y eventos.

1. Crea una página HTML con un botón que diga: "Abrir Google".
2. Al hacer clic en el botón:
   - Abre la página de Google en una nueva ventana de 500x500 píxeles.
3. Añade otro botón para **cerrar** la ventana de Google si está abierta.

---

## **Ejercicio 5: Estadísticas Avanzadas de Ventas (40 minutos)**
**Objetivo**: Repasar programación funcional con Arrays y objetos.

### **Datos Iniciales:**
Dado el siguiente array de objetos que representa las ventas de una tienda:

```javascript
const ventas = [
  { producto: "Camisa", precio: 20, cantidad: 3 },
  { producto: "Pantalón", precio: 50, cantidad: 2 },
  { producto: "Zapatos", precio: 100, cantidad: 1 },
  { producto: "Sombrero", precio: 15, cantidad: 5 },
  { producto: "Cinturón", precio: 25, cantidad: 2 },
];
```

### **Tareas:**
1. **Cálculo del Ingreso Total (reduce):**
   - Calcula el ingreso total de la tienda (precio \* cantidad) usando `reduce`.

2. **Creación de un Array de Ingresos (map):**
   - Crea un nuevo array de objetos con las propiedades `producto` e `ingreso` (precio \* cantidad) usando `map`.

3. **Productos con Ingresos Altos (filter):**
   - Filtra los productos cuyos ingresos sean mayores a 50€.

4. **Buscar un Producto (find):**
   - Busca el producto con el nombre "Zapatos" y muestra su información.

5. **Índice de un Producto (findIndex):**
   - Encuentra el índice del producto llamado "Cinturón" en el array original.

6. **Verificación de Precios (some y every):**
   - Usa `some` para comprobar si hay algún producto cuyo precio sea mayor a 100€.
   - Usa `every` para verificar si todos los productos tienen un precio mayor a 10€.

7. **Ordenación de Productos (sort):**
   - Ordena los productos por ingreso total en orden descendente.

8. **Lista de Nombres de Productos (map y join):**
   - Crea un array con los nombres de los productos.
   - Convierte ese array en un string separado por comas (ej., `"Camisa, Pantalón, Zapatos, Sombrero, Cinturón"`).

9. **Agrupación por Rango de Ingreso:**
   - Crea dos arrays:
     - Uno con los productos cuyos ingresos sean menores o iguales a 50€.
     - Otro con los productos cuyos ingresos sean mayores a 50€.

10. **Combinación de Resultados (reduce):**
    - Usando `reduce`, crea un objeto que agrupe los productos por rango de precio:
      - `barato`: Productos con precio menor o igual a 30€.
      - `caro`: Productos con precio mayor a 30€.

### **Extras Opcionales:**
- **Actualizar un Producto (map):**
  - Usa `map` para aplicar un descuento del 10% a todos los productos con un precio mayor a 50€, actualizando los precios directamente.

- **Buscar el Producto con Mayor Ingreso (reduce):**
  - Encuentra el producto con el mayor ingreso total utilizando `reduce`.

---

### **Salida Esperada:**
Cada apartado debe mostrar los resultados en la consola. Por ejemplo:
```javascript
console.log("Ingreso total:", ingresoTotal);
console.log("Productos con ingresos mayores a 50€:", productosAltos);
console.log("Producto encontrado (Zapatos):", productoZapatos);
console.log("Índice del producto 'Cinturón':", indiceCinturon);
```
