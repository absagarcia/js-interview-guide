# ❓ Preguntas técnicas - Nivel Middle

Estas preguntas están pensadas para evaluar conocimientos intermedios en JavaScript, incluyendo asincronía, manipulación avanzada de arrays, closures, contexto de ejecución y buenas prácticas modernas.

---

## 1. ¿Qué diferencia hay entre un callback y una promesa?

- **Callback**: función que se pasa como argumento y se ejecuta después.
- **Promesa**: objeto que representa el resultado futuro de una operación asincrónica.

```js
// Callback
setTimeout(() => console.log("Hecho"), 1000);

// Promesa
fetch('https://api.com')
  .then(res => res.json())
  .then(data => console.log(data));
```

---

## 2. ¿Qué es el event loop y cómo funciona?

Es el mecanismo que permite a JavaScript manejar operaciones asincrónicas sin bloquear el hilo principal. Procesa tareas en el orden:
	1.	Call Stack
	2.	Microtareas (promesas)
	3.	Macrotareas (setTimeout, setInterval)

---

## 3. ¿Qué imprime este código y por qué?

```js
console.log('Inicio');
setTimeout(() => console.log('Timeout'), 0);
Promise.resolve().then(() => console.log('Promesa'));
console.log('Fin');
```
Explicación: el console.log va al call stack primero, luego las microtareas (.then()), luego macrotareas (setTimeout).

## 4. ¿Qué es un closure y para qué sirve?

Un closure es cuando una función “recuerda” su contexto incluso después de que la función externa ha terminado de ejecutarse.

```js
function contador() {
  let count = 0;
  return () => ++count;
}
const c = contador();
c(); // 1
c(); // 2
```

---

## 5. ¿Cuál es la diferencia entre map, forEach y reduce?
	•	map: transforma cada elemento y devuelve un nuevo array.
	•	forEach: recorre sin devolver nada.
	•	reduce: reduce el array a un solo valor.

---

## 6. ¿Cómo clonas un objeto sin referencia?

```js
const original = { a: 1 };
const copia = { ...original };
```

O con JSON:

```js
const copiaProfunda = JSON.parse(JSON.stringify(original));
```

## 7. ¿Cuál es la diferencia entre == y ===?
	• ==: comparación con coerción de tipo.
	• ===: comparación estricta (tipo y valor).

```js
'5' == 5   // true
'5' === 5  // false
```

---

## 8. ¿Qué valor tiene this en una arrow function?

Hereda el this del contexto en el que fue definida.

```js
const obj = {
  nombre: "Ana",
  saludar: () => console.log(this.nombre)
};

obj.saludar(); // undefined
```

---

## 9. ¿Qué es el operador rest y spread?
	• Rest: agrupa argumentos en un array.
	• Spread: expande elementos.

```js
function suma(...nums) {
  return nums.reduce((a, b) => a + b, 0);
}

const arr = [1, 2];
const nuevoArr = [...arr, 3]; // [1, 2, 3]
```

---

## 10. ¿Cómo manejarías errores con async/await?

Usando try/catch.
```js
async function obtener() {
  try {
    const res = await fetch('https://api.com');
    const data = await res.json();
    return data;
  } catch (err) {
    console.error('Error:', err);
  }
}
```

---

## 11. ¿Qué hace Array.find()?

Devuelve el primer elemento que cumpla la condición.

```js
const nums = [1, 2, 3];
const nuevos = [...nums, 4]; // [1, 2, 3, 4]
```

---

## 13. ¿Qué es una función pura?

Una función que:
	•	No tiene efectos secundarios.
	•	Siempre devuelve el mismo resultado con los mismos argumentos.

---

14. ¿Qué son las microtareas y macrotareas?
	•	Microtareas: promesas, queueMicrotask.
	•	Macrotareas: setTimeout, setInterval, setImmediate.

---

15. ¿Qué pasa si olvidas cerrar una promesa con .catch()?

Puede causar errores silenciosos y no capturados. En entornos modernos puede lanzar una advertencia de “unhandled promise rejection”.

---

## 16. ¿Qué es currying?

Transformar una función con varios argumentos en una cadena de funciones con un solo argumento.

```js
function sumar(a) {
  return function (b) {
    return a + b;
  };
}

sumar(2)(3); // 5
```

---

## 17. ¿Cuál es la diferencia entre null y undefined?
	•	undefined: valor no asignado.
	•	null: valor intencionalmente vacío.

---

## 18. ¿Qué hace el operador typeof?

Devuelve el tipo de un valor como string.

```js
typeof "hola"     // "string"
typeof undefined  // "undefined"
typeof null       // "object" (!)
typeof (() => {}) // "function"
```

---

## 19. ¿Cómo usarías destructuring con objetos?

```js
const user = { nombre: "Ana", edad: 25 };
const { nombre } = user;
```

---

## 20. ¿Qué es el principio de responsabilidad única?

Cada función debe hacer una sola cosa y hacerla bien. Esto mejora la mantenibilidad y reutilización del código.
