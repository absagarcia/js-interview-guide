# 🧠 Conceptos clave - Nivel Middle

Este documento cubre temas intermedios de JavaScript que todo desarrollador con experiencia práctica debe conocer para destacar en entrevistas técnicas o proyectos reales.

---

## 🧩 Funciones de Orden Superior

Funciones que reciben o devuelven otras funciones. Son clave en programación funcional.

```js
const duplicar = n => n * 2;
const resultado = [1, 2, 3].map(duplicar); // [2, 4, 6]
```

---

## 🌀 Callbacks vs Promesas vs Async/Await
	•	Callback: función que se pasa como argumento para ejecutarse más tarde.
	•	Promesa: estructura para manejar asincronía.
	•	async/await: azúcar sintáctico para escribir código asincrónico de forma más limpia.

---

## 🧠 Event Loop y Micro/Macrotareas

El Event Loop permite que JS sea no bloqueante. Procesa:
	•	Call Stack
	•	Microtareas: .then(), await
	•	Macrotareas: setTimeout, setInterval

Orden: Call Stack → Microtasks → Macrotasks.

---

## 🔄 Métodos avanzados de Array
	•	map(), filter(), reduce(), find()
	•	some(), every(), sort(), flat()
	•	forEach() (no retorna nada)

```js
const productos = [
  { nombre: 'Camisa', precio: 20 },
  { nombre: 'Pantalón', precio: 30 }
];

const total = productos.reduce((acc, item) => acc + item.precio, 0);
```

---

## 🧱 Destructuring y Spread/Rest
	•	Destructuring: extrae propiedades/valores.

```js
const user = { nombre: 'Ana', edad: 25 };
const { nombre } = user;
```

	•	Spread/Rest:

```js
const arr1 = [1, 2];
const arr2 = [...arr1, 3]; // Spread

function sumar(...nums) { return nums.reduce((a, b) => a + b); } // Rest
```

---

## 📦 Modularización
	•	CommonJS: require, module.exports
	•	ES Modules: import, export (recomendado)

---

## 🏗️ Scope y Closures
	•	Scope: determina la accesibilidad de variables.
	•	Closures: una función que recuerda su entorno.

---

## 🧭 this y el contexto de ejecución
	•	this depende de cómo se llama una función.
	•	En arrow functions, this se hereda del contexto.

---

## 🧪 Testing básico
	•	Frameworks: Jest, Vitest
	•	Test unitarios y de integración.

```js
test('suma dos números', () => {
  expect(1 + 2).toBe(3);
});
```

---

## 🌐 Fetch API y manejo de errores

```js
fetch('https://api.com/data')
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => console.error(err));
```

---

## 🗃️ LocalStorage vs SessionStorage
	•	localStorage: persiste hasta que se borre manualmente.
	•	sessionStorage: se borra al cerrar la pestaña.

⸻

## 🧩 Tipos de igualdad
	•	==: igualdad laxa (coerción)
	•	===: igualdad estricta (sin coerción)

⸻

## 🚧 Coerción de tipos

```js
'5' + 1    // '51'
'5' - 1    // 4
true + 1   // 2
false == 0 // true
```

