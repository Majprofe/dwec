# Práctica de Testing en JavaScript con Vitest

Este documento contiene casos de prueba guiados basados en el video de midudev. Estos ejercicios están diseñados para aprender a usar Vitest para probar funciones y aplicaciones de JavaScript.

---

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

describe("fizzbuzz", () => {
    it('should be a function', () => {
        expect(typeof fizzbuzz).toBe('function');
    });

    it('should throw if not number is provided as parameter', () => {
        expect(() => fizzbuzz()).toThrow()
    });

    it('should throw a specific error message if not number is provided as parameter', () => {
        expect(() => fizzbuzz()).toThrow(/number/)
    });

    it('should return 1 if number provided is 1', () => {
        expect(fizzbuzz(1)).toBe(1);
    });

    it('should return 2 if number provided is 2', () => {
        expect(fizzbuzz(2)).toBe(2);
    });

    it('should return fizz if number provided is 3', () => {
        expect(fizzbuzz(3)).toBe('fizz');
    });

    it('should return fizz if number provided is multiple of 3', () => {
        expect(fizzbuzz(6)).toBe('fizz');
        expect(fizzbuzz(9)).toBe('fizz');
        expect(fizzbuzz(12)).toBe('fizz');
    });

    it('should return 4 if number provided is 4', () => {
        expect(fizzbuzz(4)).toBe(4);
    });

    it('should return buzz if number provided is 5', () => {
        expect(fizzbuzz(5)).toBe('buzz');
    });

    it('should return buzz if number provided is multiple of 5', () => {
        expect(fizzbuzz(10)).toBe('buzz');
        expect(fizzbuzz(25)).toBe('buzz'); //Si elegimos 15 sería también múltiplo de 3 y 5
        expect(fizzbuzz(20)).toBe('buzz');
    });

    it('should return fizzbuzz if number provided is multiple of 3 and 5', () => {
        expect(fizzbuzz(15)).toBe('fizzbuzz');
        expect(fizzbuzz(30)).toBe('fizzbuzz');
        expect(fizzbuzz(45)).toBe('fizzbuzz');
    });
})
```

### Paso 4: Ejecutar las pruebas
Ejecuta el comando:

```bash
npm test
```

Deberías ver que todas las pruebas pasan correctamente.

---

## **Caso 2: Validar una contraseña segura**

### Descripción
Implementaremos una función que valide si una contraseña es segura. La contraseña debe tener:
- Al menos 8 caracteres.
- Una letra mayúscula.
- Un número.

### Paso 1: Crear la función
Crea un archivo llamado `passwordValidator.js`:

```javascript
// passwordValidator.js
export const isPasswordSecure = (password) => {
  if (typeof password !== 'string') throw new Error('La contraseña debe ser un string');
  return (
    password.length >= 8 &&
    /[A-Z]/.test(password) &&
    /[0-9]/.test(password)
  );
};
```

### Paso 2: Crear el archivo de prueba
Crea un archivo llamado `passwordValidator.test.js`:

```javascript
// passwordValidator.test.js
import { describe, it, expect } from 'vitest';
import { isPasswordSecure } from './passwordValidator';

describe('isPasswordSecure', () => {
  it('debería devolver true para contraseñas seguras', () => {
    expect(isPasswordSecure('Password1')).toBe(true);
    expect(isPasswordSecure('Secure123')).toBe(true);
  });

  it('debería devolver false para contraseñas inseguras', () => {
    expect(isPasswordSecure('pass')).toBe(false);
    expect(isPasswordSecure('password')).toBe(false);
    expect(isPasswordSecure('Password')).toBe(false);
  });

  it('debería lanzar un error si el argumento no es un string', () => {
    expect(() => isPasswordSecure(12345678)).toThrow('La contraseña debe ser un string');
  });
});
```

---

## **Caso 3: Verificar números primos**

### Descripción
Crearemos una función que determine si un número es primo y la probaremos.

### Paso 1: Crear la función
Crea un archivo llamado `isPrime.js`:

```javascript
// isPrime.js
export const isPrime = (num) => {
  if (typeof num !== 'number' || num < 2) return false;
  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (num % i === 0) return false;
  }
  return true;
};
```

### Paso 2: Crear el archivo de prueba
Crea un archivo llamado `isPrime.test.js`:

```javascript
// isPrime.test.js
import { describe, it, expect } from 'vitest';
import { isPrime } from './isPrime';

describe('isPrime', () => {
  it('debería devolver true para números primos', () => {
    expect(isPrime(2)).toBe(true);
    expect(isPrime(3)).toBe(true);
    expect(isPrime(7)).toBe(true);
  });

  it('debería devolver false para números no primos', () => {
    expect(isPrime(1)).toBe(false);
    expect(isPrime(4)).toBe(false);
    expect(isPrime(9)).toBe(false);
  });

  it('debería devolver false para números menores que 2 o no numéricos', () => {
    expect(isPrime(-1)).toBe(false);
    expect(isPrime(0)).toBe(false);
    expect(isPrime('7')).toBe(false);
  });
});
```

---

## **Caso 4: Calcular la media de un array**

### Descripción
Implementaremos una función que calcule la media de un array de números.

### Paso 1: Crear la función
Crea un archivo llamado `average.js`:

```javascript
// average.js
export const average = (numbers) => {
  if (!Array.isArray(numbers)) throw new Error('El argumento debe ser un array');
  if (numbers.length === 0) return 0;
  return numbers.reduce((acc, num) => acc + num, 0) / numbers.length;
};
```

### Paso 2: Crear el archivo de prueba
Crea un archivo llamado `average.test.js`:

```javascript
// average.test.js
import { describe, it, expect } from 'vitest';
import { average } from './average';

describe('average', () => {
  it('debería calcular la media de un array de números', () => {
    expect(average([1, 2, 3, 4, 5])).toBe(3);
    expect(average([10, 20, 30])).toBe(20);
  });

  it('debería devolver 0 para un array vacío', () => {
    expect(average([])).toBe(0);
  });

  it('debería lanzar un error si el argumento no es un array', () => {
    expect(() => average('12345')).toThrow('El argumento debe ser un array');
  });
});
```


