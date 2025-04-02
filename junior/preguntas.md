# ❓ Preguntas técnicas - Nivel Junior

A continuación, una serie de preguntas comunes que te pueden hacer en entrevistas de nivel junior para desarrollador JavaScript.

---

## 1. ¿Cuál es la diferencia entre `let`, `const` y `var`?

`let` y `const` tienen **alcance de bloque**, mientras que `var` tiene **alcance de función**.  
`const` no permite reasignación y requiere una inicialización.  
`var` permite redeclaración, lo cual puede causar errores.

---

## 2. ¿Qué es hoisting?

Es el comportamiento de JavaScript donde las **declaraciones** de variables y funciones son "elevadas" al inicio de su contexto de ejecución.

```js
console.log(x); // undefined
var x = 10;
```
---

## 3. ¿Qué es una función de orden superior?

Una función que puede recibir otras funciones como argumentos o devolver funciones.

``` js
function operar(fn) {
  return fn(2, 3);
}
operar((a, b) => a + b); // 5
```

---

## 4. ¿Cuál es la diferencia entre == y ===?
	•	==: compara solo valor (con conversión de tipos).
	•	===: compara valor y tipo (estricta).
```js
'5' == 5   // true
'5' === 5  // false
```

---

## 5. ¿Cómo agregarías un evento click a un botón?

```js
document.getElementById('miBoton').addEventListener('click', () => {
  console.log('¡Clic!');
});
```

---

## 6. ¿Qué es el objeto event?

Es un objeto que representa el evento que ocurrió. Se puede usar para acceder al elemento que lo generó (event.target) y controlar su comportamiento.

---

## 7. ¿Qué métodos de array conoces?
	•	map
	•	filter
	•	reduce
	•	forEach
	•	some
	•	every
	•	find
	•	includes
	•	sort

---

## 8. ¿Qué es JSON.stringify() y JSON.parse()?
	•	JSON.stringify(): convierte un objeto JavaScript a una cadena JSON.
	•	JSON.parse(): convierte una cadena JSON a un objeto JavaScript.

```js
const obj = { nombre: "Ana", edad: 30 };
const json = JSON.stringify(obj);
const parsed = JSON.parse(json);
```

---

## 9. ¿Qué hace typeof?

Devuelve el tipo de dato de una variable.

```js
typeof 42           // "number"
typeof 'Hola'       // "string"
typeof true         // "boolean"
typeof undefined    // "undefined"
typeof null         // "object" (quirk de JS)
typeof {}           // "object"
typeof []           // "object"
typeof (() => {})   // "function"
```

---

## 10. ¿Qué es el DOM?

El DOM (Document Object Model) es una representación estructurada del documento HTML, que permite a JavaScript acceder y manipular los elementos del documento (nodos).

```js
document.querySelector('h1').textContent = 'Hola mundo';
```

---

## 11. ¿Qué es una función anónima?

Es una función sin nombre que se suele usar como argumento o función de retorno.

```js
const saludo = function () {
  console.log("Hola");
};
```

---

## 12. ¿Qué es una arrow function y qué ventajas tiene?

Es una forma concisa de declarar funciones. No tiene su propio this, ni arguments, ni se puede usar como constructor.

```js
const sumar = (a, b) => a + b;
```

---

## 14. ¿Y el operador rest?

Agrupa parámetros en un solo array.

```js
function sumar(...nums) {
  return nums.reduce((a, b) => a + b, 0);
}
```

---

## 15. ¿Qué diferencia hay entre null y undefined?
	•	undefined: valor no asignado.
	•	null: valor intencionalmente vacío.

---

## 16. ¿Qué son las plantillas literales (template literals)?

Permiten insertar variables en strings usando backticks ` y ${}.

```js
const nombre = "Ana";
console.log(`Hola, ${nombre}`);
```

## 17. ¿Para qué sirve Array.map()?

Crea un nuevo array transformando cada elemento.

```js
[1, 2, 3].map(n => n * 2); // [2, 4, 6]
```

---

## 18. ¿Qué hace Array.filter()?

Filtra los elementos que cumplen una condición.
```js
[1, 2, 3].filter(n => n > 1); // [2, 3]
```

---

## 19. ¿Y Array.reduce()?

Reduce todos los valores a uno solo.

```js
[1, 2, 3].reduce((acc, n) => acc + n, 0); // 6
```

---

## 20. ¿Qué es falsy y truthy?
	•	Falsy: valores que se evalúan como false: false, 0, '', null, undefined, NaN.
	•	Truthy: todo lo demás.

---

## 21. ¿Cómo se usa setTimeout y setInterval?

```js
setTimeout(() => console.log('Hola'), 1000); // Una vez
setInterval(() => console.log('Repetir'), 2000); // Cada 2s
```

---

## 22. ¿Qué hace clearTimeout y clearInterval?

Cancela un temporizador.

```js
const id = setTimeout(() => {}, 1000);
clearTimeout(id);
```

---
## 23. ¿Cómo se accede a atributos de un objeto?

```js
const persona = { nombre: "Ana" };
console.log(persona.nombre);     // "Ana"
console.log(persona["nombre"]); // "Ana"
```

---

## 24. ¿Qué hace Array.includes()?

Verifica si un elemento está en el array.

```js
[1, 2, 3].includes(2); // true
```

---

## 25. ¿Qué es NaN?

Significa “Not a Number”, indica un resultado inválido de operación numérica.

```js
parseInt("hola"); // NaN
```

---

## 26. ¿Qué hace isNaN()?

Verifica si el valor es NaN.

```js
isNaN("hola"); // true
```

## 27. ¿Para qué se usa try/catch?

Para manejar errores sin detener la ejecución del programa.

```js
try {
  throw new Error("Fallo");
} catch (err) {
  console.log(err.message);
}
```

---

## 28. ¿Qué es una promesa?

Es una forma de manejar operaciones asincrónicas.

```js
const promesa = new Promise((resolve, reject) => {
  resolve("OK");
});
```

---

## 29. ¿Cómo se usa .then() y .catch()?

```js
promesa
  .then((res) => console.log(res))
  .catch((err) => console.log(err));
```

---

## 30. ¿Cómo se declara una función async/await?

```js
async function obtenerDatos() {
  const res = await fetch('https://api');
  const data = await res.json();
  return data;
}
```

---

