# Testing

## Tabla de contenidos

1. [Introducción a los Mocks](#introducción-a-los-mocks)
2. [¿Cuándo usar Mocks?](#cuándo-usar-mocks)
3. [Ejemplo básico: Simular una función](#ejemplo-básico-simular-una-función)
   - [Explicación paso a paso](#explicación-paso-a-paso)
4. [Simular el comportamiento de una función](#simular-el-comportamiento-de-una-función)
5. [Simular módulos completos](#simular-módulos-completos)
6. [Espías (Spies)](#espías-spies)
7. [Practicas propuestas](#prácticas-de-ejemplo)

---
  
## Introducción al Testing

El testing es fundamental para garantizar la calidad del código, minimizando fallos y asegurando que se comporta como se espera. A medida que las aplicaciones crecen en complejidad, el testing se vuelve indispensable. Sus ventajas incluyen:

- **Detección de errores:** Validar que el código responde correctamente.
- **Prevención de errores de regresión:** Evitar fallos en funciones que previamente funcionaban.
- **Documentación implícita:** Los tests describen el comportamiento esperado del código.

### Tipos de Testing

1. **Unitarios:** Prueban funciones individuales de forma aislada.
2. **Integración:** Validan la interacción entre múltiples módulos.
3. **Aceptación:** Garantizan que el sistema satisface los requisitos del cliente.

Cada test sigue este patrón:
- **Preparación (_Arrange_):** Configurar los datos o condiciones necesarias.
- **Ejecución (_Act_):** Invocar la función a probar.
- **Aserción (_Assert_):** Verificar que el resultado es el esperado.

Ejemplo básico:

```javascript
test('wordCount() returns 2 when the input is "Hello world"', () => {
  // Arrange
  const string = 'Hello world';

  // Act
  const result = wordCount(string);

  // Assert
  expect(result).toBe(2);
});
```

---

## Desarrollo guiado por pruebas (TDD)
Es una forma de programar que consiste en escribir primero las pruebas que deba pasar el código (Test Dirve Development) y luego el código que las pase. Por último deberíamos refactorizarlo ([Refactoring](https://es.wikipedia.org/wiki/Refactorizaci%C3%B3n)). Para escribir las pruebas generalmente se utilizan las [pruebas unitarias](https://es.wikipedia.org/wiki/Prueba_unitaria) (unit test en inglés). 

El ciclo de programación usando TDD tiene tres fases:
1. Fase _roja_: escribimos el test que cumpla los requerimientos y lo pasamos. Fallará ya que nuestro código no pasa el test (de hecho la primera vez no tenemos ni código)
1. Fase _verde_: conseguimos que nuestro código pase el test. Ya funciona aunque seguramente no estará muy bien escrito
1. _Refactorización_: mejoramos nuestro código

Ejemplo de TDD:

```javascript
// Test
test('debería sumar correctamente', () => {
  expect(sumar(2, 3)).toBe(5);
});

// Implementación
function sumar(a, b) {
  return a + b;
}
```

En primer lugar, se escribe una prueba y se verifica que las pruebas fallan. A continuación, se implementa el código que hace que la prueba pase satisfactoriamente y seguidamente se refactoriza el código escrito. El propósito del desarrollo guiado por pruebas es lograr un código limpio que funcione. La idea es que los requisitos sean traducidos a pruebas, de este modo, cuando las pruebas pasen se garantizará que el software cumple con los requisitos que se han establecido.

(Fuente [Wikipedia](https://es.wikipedia.org/wiki/Desarrollo_guiado_por_pruebas)).

## Testing en Javascript
Algunos de los frameworks más utilizados para realizar pruebas en JavaScript son:
- Jasmine
- Mocha + Chai
- Jest
- Selenium
- Puppeteer
- Vitest

Nosotros usaremos **_Vitest_** porque se integra fácilmente en Vite y porque tiene algunas características de suites más modernas, en especial su facilidad de uso, su facilidad de emular a un navegador y su funcionamiento nativo con módulos ES6.  

### Instalación de npm

npm (Node Package Manager) es esencial para gestionar dependencias en proyectos JavaScript. Para instalar npm, primero necesitas Node.js. Sigue las instrucciones en la [página oficial de Node.js](https://nodejs.org/es/download/package-manager/) para instalarlo según tu sistema operativo.

---

## Vitest
Vitest es un framework de pruebas unitarias moderno diseñado para entornos basados en Vite, pero puede utilizarse en cualquier proyecto de JavaScript. Ofrece una sintaxis sencilla y soporte para TypeScript, mocks, spies y más.

### Instalación de Vitest
Para instalar Vitest, utilizamos el siguiente comando:
```bash
npm install -D vitest
```
Debemos crear archivos de prueba que tengan la extensión .test.js.

Si estás usando Vite, puedes añadir el siguiente bloque al vite.config.js o vite.config.ts:
```javascript
/// vite.config.js
import { defineConfig } from 'vite';

export default defineConfig({
  test: {
    globals: true, // Habilita los métodos globales como `describe` y `it`.
    environment: 'jsdom', // Para pruebas que involucren el DOM.
  },
});
```
Después de instalarlo, en el package.json debemos ver la siguiente informaicón:
```json
{
  "scripts": {
    "test": "vitest",
    "coverage": "vitest run --coverage"
  }
}
```
Podemos ejecutar las pruebas y obtener informes de cobertura de código con los siguientes comandos:
```bash
npm run test
npm run coverage
npx vitest --ui
```
Ejemplo básico con Vitest:

```javascript
import { describe, it, expect } from 'vitest';

describe('Nombre del grupo de pruebas', () => {
  it('debería hacer algo correctamente', () => {
    const resultado = 2 + 2;
    expect(resultado).toBe(4);
  });
});
```

---
## Usar Vitest
### Matchers
Los más comunes son:
- **toBe()**: compara el resultado del _expect_ con lo que le pasamos como parámetro. Sólo sirve para valores primitivos (number, string, boolean, ...) no para arrays ni objetos
- **toBeCLoseTo()**: se usa para números de punto flotante. `expect(0.1 + 0.2).toBe(0.3)` no se usa toBe en números decimales porque javascript no los compara bien
- **toEqual()**: como el anterior pero para objetos y arrays. Comprueba cada uno de los elementos el objeto o array
- **toBeLessThan**, **toBeLessThanOrEqual**, **toBeGreaterThan**, **toBeGreaterThanOrEqual**: para comparaciones <, <=, >, >=
- **toBeTruthy**: el valor devuelvo es verdadero o asimilable a verdadero (si fuera la condición de un _if_ se ejecutaría el _then_)
- **toBeFalsy**: el valor devuelvo es falso o asimilable a falso (si fuera la condición de un _if_ se ejecutaría el _else_)
- **toBeUndefined**: el valor es _undefined_
- **toBeDefined**: el valor NO es _undefined_
- **toBeNull**: el valor devuelto es _null_
- **toMatch**: el valor devuelto debe cumplir con la expresión regular pasada
- **toContain**: el array devuelto debe contener el elemento pasado como parámetro
- **toHaveLength**: el array o el string devueltos debe tener la longitud indicada

Para comprobar si una función lanza una excepción, se usa `toThrow`. Puedes verificar si:
1. Se lanzó cualquier error.
2. El error es de un tipo específico.
3. El mensaje del error coincide exactamente o cumple con una expresión regular.
```javascript
function compileAndroidCode() {
  throw new Error('you are using the wrong JDK');
}

test('compiling android goes as expected', () => {
  expect(compileAndroidCode).toThrow();
  expect(compileAndroidCode).toThrow(Error);
  expect(compileAndroidCode).toThrow('you are using the wrong JDK');
  expect(compileAndroidCode).toThrow(/JDK/);
});
```

Podemos obtener la lista completa de _matchers_ en al [documentación oficial de Vitest](https://vitest.dev/api/expect.html).

### Pruebas asíncronas
Vitest soporta pruebas con funciones asíncronas usando `async/await`:
```javascript
describe('Test Promesas', function() {
  describe('incrementar decrementar', function() {
    test('should return the number +1', async function() {
      expect(await incrementar(1)).toBe(2);
      expect(await incrementar(1000)).toBe(1001);
    });
    test('should return the number -1', async function() {
      expect(await decrementar(1)).toBe(0);
      expect(await decrementar(1000)).toBe(999);
    });
  });
});
```
Hay un problema con las promesas, si no se cumplen nunca, el test no acaba y tampoco falla. En caso de que pueda pasar eso, se puede usar setTimeOut con un tiempo razonable y dar fallo si no se cumple en ese plazo. Usa `Promise.race` para manejar tiempos de espera:
```javascript
const timeout = (ms) => new Promise((_, reject) => setTimeout(() => reject(new Error('Timeout exceeded')), ms));
const result = await Promise.race([increment(1), timeout(5000)]);
expect(result).toBe(2);
```

---

### Test suites
En muchas ocasiones no vamos a pasar un único test sino un conjunto de ellos. En ese caso podemos agruparlos en un _test suite_ que definimos con la instruacción `describe` a la que pasamos un nombre que la describa y una función que contiene todos los tests a pasar:

```javascript
import { describe, it, expect } from 'vitest';

const sumar = (a, b) => a + b;

describe('Pruebas para la función sumar', () => {
  it('debería sumar dos números correctamente', () => {
    const resultado = sumar(2, 3);
    expect(resultado).toBe(5);
  });

  it('debería devolver un número negativo si ambos números son negativos', () => {
    const resultado = sumar(-2, -3);
    expect(resultado).toBe(-5);
  });
});
```

## Mocks

Los **mocks** son funciones simuladas que reemplazan la implementación de funciones reales para controlar su comportamiento durante los tests. Esto es útil cuando queremos:

1. Evitar ejecutar funciones reales (como llamadas a APIs o interacciones con el DOM).
2. Verificar si una función se ha llamado, cuántas veces y con qué parámetros.
3. Simular resultados específicos que puedan ser difíciles de reproducir.

### ¿Cuándo usar mocks?

1. **Evitar efectos secundarios:** Por ejemplo, si una función interactúa con una base de datos o realiza una operación que modifica el estado global.
2. **Aislar dependencias:** Cuando estamos probando una unidad de código que depende de otra, queremos asegurarnos de que la unidad probada sea la única que se evalúa.
3. **Simular errores:** Para asegurarnos de que el código maneja correctamente los fallos, podemos usar mocks para devolver errores específicos.

### Ejemplo básico: Simular una función

En este ejemplo, tenemos un método de un controlador llamado `addProduct` que llama a otro de la vista llamado `renderProduct` para renderizar algo. Queremos probar si `renderProduct` se llama correctamente sin ejecutar la función real.

```javascript
import { vi, describe, it, expect } from 'vitest';

// Crear un mock de la función renderProduct
const renderProduct = vi.fn();

describe('Mocks en Vitest', () => {
  it('debería llamar a renderProduct dos veces con los argumentos correctos', () => {
    const product = { id: 1, name: "Prod 1", price: 49.99 };

    // Llamadas a la función mock
    renderProduct(product);
    renderProduct({});

    // Verificar el número de llamadas
    expect(renderProduct).toHaveBeenCalledTimes(2);

    // Verificar los argumentos de las llamadas
    expect(renderProduct).toHaveBeenNthCalledWith(1, product);
    expect(renderProduct).toHaveBeenNthCalledWith(2, {});
  });
});
```

### Explicación paso a paso

1. **Crear un mock:**  
   Usamos `vi.fn()` para crear una función simulada llamada `renderProduct`.

2. **Ejecutar pruebas:**  
   Llamamos al mock con diferentes argumentos.

3. **Verificaciones:**  
   - `toHaveBeenCalledTimes`: Comprueba cuántas veces se ha llamado a la función.
   - `toHaveBeenNthCalledWith`: Verifica los argumentos de una llamada específica.

---

### Simular el comportamiento de una función

Los mocks no solo verifican si una función ha sido llamada, también pueden simular su comportamiento usando `mockImplementation`.

```javascript
const fetchData = vi.fn((url) => {
  if (url === 'https://api.example.com/data') {
    return { id: 1, name: 'Item 1' };
  }
  throw new Error('Not Found');
});

describe('Mocks con implementación personalizada', () => {
  it('debería devolver datos para una URL válida', () => {
    const result = fetchData('https://api.example.com/data');
    expect(result).toEqual({ id: 1, name: 'Item 1' });
  });

  it('debería lanzar un error para una URL inválida', () => {
    expect(() => fetchData('https://api.example.com/invalid')).toThrow('Not Found');
  });
});
```

---

### Simular módulos completos

Vitest permite simular módulos completos usando `vi.mock()`. Esto es útil para reemplazar dependencias externas.

```javascript
// Simular un módulo externo
vi.mock('./miModulo', () => ({
  fetchData: vi.fn(() => Promise.resolve({ id: 1, name: 'Mocked Item' })),
}));

import { fetchData } from './miModulo';

describe('Mocks de módulos', () => {
  it('debería devolver datos simulados', async () => {
    const data = await fetchData();
    expect(data).toEqual({ id: 1, name: 'Mocked Item' });
  });
});
```

---

### Espías (Spies)

Los **spies** permiten espiar funciones reales en lugar de reemplazarlas por mocks completos. Usamos `vi.spyOn()` para capturar llamadas y argumentos de una función existente.

```javascript
const logger = {
  log: (message) => console.log(message),
};

describe('Espías en Vitest', () => {
  it('debería registrar un mensaje en la consola', () => {
    const spy = vi.spyOn(logger, 'log');

    logger.log('Mensaje de prueba');

    expect(spy).toHaveBeenCalledWith('Mensaje de prueba');
    spy.mockRestore(); // Restaurar la implementación original
  });
});
```
---

## Prácticas de ejemplo

1. Testing de la función [FizzBuzz](./ejemplosclase/13-tests-fizzbuzz.md)