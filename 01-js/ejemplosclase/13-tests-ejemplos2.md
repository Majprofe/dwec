
# Práctica de Testing en JavaScript con Vitest

Este documento contiene casos de prueba guiados basados en el video de midudev y ejemplos adaptados de tus apuntes. Estos ejercicios están diseñados para aprender a usar Vitest para probar funciones y aplicaciones de JavaScript.

---

## **Ejercicio 1: Mock simulando una llamada con vi.fn()**

### Descripción
Simularemos una función que procesa datos mediante un callback y probaremos su comportamiento utilizando `vi.fn()`.

### Paso 1: Crear la función
Crea un archivo llamado `processData.js`:

```javascript
// processData.js
export const processData = (data, callback) => {
  if (!data) throw new Error('No hay datos para procesar');
  return callback(data);
};
```

### Paso 2: Crear el archivo de prueba
Crea un archivo llamado `processData.test.js`:

```javascript
// processData.test.js
import { describe, it, expect, vi } from 'vitest';
import { processData } from './processData';

describe('processData', () => {
  it('debería llamar al callback con los datos correctos', () => {
    const mockCallback = vi.fn((data) => data.toUpperCase());
    const result = processData('texto', mockCallback);

    expect(mockCallback).toHaveBeenCalledWith('texto');
    expect(result).toBe('TEXTO');
  });

  it('debería lanzar un error si no se proporcionan datos', () => {
    expect(() => processData(null, vi.fn())).toThrow('No hay datos para procesar');
  });
});
```

---

## **Ejercicio 2: Mock simulando módulos completos con vi.mock()**

### Descripción
Simularemos un módulo completo para realizar operaciones matemáticas usando `vi.mock()`.

### Paso 1: Crear el módulo
Crea un archivo llamado `math.js`:

```javascript
// math.js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;
export const multiply = (a, b) => a * b;
export const divide = (a, b) => {
  if (b === 0) throw new Error('No se puede dividir por cero');
  return a / b;
};
```

### Paso 2: Crear el archivo de prueba
Crea un archivo llamado `math.test.js`:

```javascript
// math.test.js
import { describe, it, expect, vi } from 'vitest';

vi.mock('./math', () => ({
  add: vi.fn((a, b) => a + b),
  subtract: vi.fn((a, b) => a - b),
  multiply: vi.fn((a, b) => a * b),
  divide: vi.fn((a, b) => (b === 0 ? 'Error' : a / b)),
}));

import { add, divide } from './math';

describe('math', () => {
  it('debería simular la función add correctamente', () => {
    const result = add(2, 3);
    expect(result).toBe(5);
    expect(add).toHaveBeenCalledWith(2, 3);
  });

  it('debería simular la función divide y manejar división por cero', () => {
    const result = divide(10, 0);
    expect(result).toBe('Error');
    expect(divide).toHaveBeenCalledWith(10, 0);
  });
});
```

---

## **Ejercicio 3: Probar llamadas a funciones con Spy**

### Descripción
Espiaremos una función para verificar si fue llamada y con qué argumentos.

### Paso 1: Crear la función
Crea un archivo llamado `logger.js`:

```javascript
// logger.js
export const logger = {
  log: (message) => {
    console.log(message);
  },
};
```

### Paso 2: Crear el archivo de prueba
Crea un archivo llamado `logger.test.js`:

```javascript
// logger.test.js
import { describe, it, expect, vi } from 'vitest';
import { logger } from './logger';

describe('logger', () => {
  it('debería llamar a console.log con el mensaje correcto', () => {
    const spy = vi.spyOn(console, 'log');
    logger.log('Hola Mundo');

    expect(spy).toHaveBeenCalledWith('Hola Mundo');

    spy.mockRestore();
  });
});
```

---

## **Comparación rápida de herramientas de Vitest**

| Herramienta       | ¿Qué hace?                                                                                        | Ejemplo de uso                                   |
|--------------------|--------------------------------------------------------------------------------------------------|-------------------------------------------------|
| **`vi.fn()`**      | Crea una función simulada que registra llamadas y devuelve valores controlados.                  | Simular callbacks o funciones independientes.   |
| **`vi.mock()`**    | Reemplaza todo un módulo o partes de él con implementaciones simuladas.                          | Simular dependencias externas completas.        |
| **`vi.spyOn()`**   | Observa una función existente sin reemplazarla, registrando llamadas y argumentos.               | Verificar el uso de funciones existentes.       |

---

Estos ejercicios cubren el uso de mocks y spies en Vitest, proporcionando herramientas esenciales para pruebas avanzadas. Asegúrate de adaptarlos según las necesidades de tus proyectos.
