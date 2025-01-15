# Práctica de Testing en JavaScript con Vitest - FizzBuzz

## **Caso 1: Probar la función FizzBuzz**

### Descripción
Vamos a implementar la función FizzBuzz y escribir pruebas para validar que se comporta correctamente. Esta función devuelve:
- "fizz" si el número es divisible por 3.
- "buzz" si el número es divisible por 5.
- "fizzbuzz" si el número es divisible por 3 y 5.
- El número en cualquier otro caso.

### Paso 1: Crear la función
Crea un archivo llamado `fizzbuzz.js` con la siguiente implementación:

```javascript
// fizzbuzz.js
export const fizzbuzz = (num) => {
  if (typeof num !== 'number') throw new Error('El argumento debe ser un número');
  if (num % 3 === 0 && num % 5 === 0) return 'fizzbuzz';
  if (num % 3 === 0) return 'fizz';
  if (num % 5 === 0) return 'buzz';
  return num;
};
```

### Paso 2: Configurar el entorno de pruebas
Asegúrate de tener Vitest instalado en tu proyecto. Si no lo tienes, instálalo con:

```bash
npm install vitest --save-dev
```

Añade el siguiente script en tu `package.json` para ejecutar las pruebas:

```json
"scripts": {
  "test": "vitest"
}
```

### Paso 3: Crear el archivo de prueba
Crea un archivo llamado `fizzbuzz.test.js` con las siguientes pruebas:

```javascript
// fizzbuzz.test.js
import { describe, it, expect } from 'vitest';
import { fizzbuzz } from './fizzbuzz';

describe('fizzbuzz', () => {
  it('debería devolver el número si no es divisible por 3 ni por 5', () => {
    expect(fizzbuzz(1)).toBe(1);
    expect(fizzbuzz(2)).toBe(2);
  });

  it('debería devolver "fizz" si el número es divisible por 3', () => {
    expect(fizzbuzz(3)).toBe('fizz');
    expect(fizzbuzz(6)).toBe('fizz');
  });

  it('debería devolver "buzz" si el número es divisible por 5', () => {
    expect(fizzbuzz(5)).toBe('buzz');
    expect(fizzbuzz(10)).toBe('buzz');
  });

  it('debería devolver "fizzbuzz" si el número es divisible por 3 y por 5', () => {
    expect(fizzbuzz(15)).toBe('fizzbuzz');
    expect(fizzbuzz(30)).toBe('fizzbuzz');
  });

  it('debería lanzar un error si el argumento no es un número', () => {
    expect(() => fizzbuzz('15')).toThrow('El argumento debe ser un número');
    expect(() => fizzbuzz(null)).toThrow('El argumento debe ser un número');
  });
});
```

### Paso 4: Ejecutar las pruebas
Ejecuta el comando:

```bash
npm test
```

Deberías ver que todas las pruebas pasan correctamente.

---

## Resumen
Este ejercicio cubre los siguientes aspectos fundamentales del testing:
1. Validar múltiples escenarios para una función.
2. Manejar errores cuando los argumentos no son válidos.
3. Escribir pruebas completas utilizando TDD.

Asegúrate de adaptar y expandir estas prácticas según las necesidades de tus proyectos.

