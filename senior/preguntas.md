# ❓ Preguntas técnicas - Nivel Senior

Estas preguntas están orientadas a evaluar la experiencia, comprensión profunda del lenguaje y habilidades de resolución de problemas en contextos complejos.

---

## 1. ¿Cómo manejarías un memory leak en una aplicación web?

Primero, identificando el leak usando herramientas como Chrome DevTools (panel de memoria, snapshots, performance). Luego, verificando:

- Listeners no eliminados
- Objetos globales
- Closures con referencias colgantes
- Intervalos no limpiados

---

## 2. Explica la diferencia entre microtasks y macrotasks con un ejemplo.

- **Microtasks**: `.then()`, `await`, `queueMicrotask`
- **Macrotasks**: `setTimeout`, `setInterval`

```js
console.log('Inicio');

setTimeout(() => console.log('Timeout'), 0);

Promise.resolve().then(() => console.log('Microtask'));

console.log('Fin');
```

Resultado:
Inicio
Fin
Microtask
Timeout

---

## 3. ¿Cómo implementarías un debounce y un throttle?

Debounce:
```js
function debounce(fn, delay) {
  let timer;
  return (...args) => {
    clearTimeout(timer);
    timer = setTimeout(() => fn(...args), delay);
  };
}
```

Throttle:
```js
function throttle(fn, limit) {
  let waiting = false;
  return (...args) => {
    if (!waiting) {
      fn(...args);
      waiting = true;
      setTimeout(() => waiting = false, limit);
    }
  };
}
```

---

## 4. ¿Qué patrones de diseño has utilizado y cuándo?

Ejemplos:
	•	Factory: para instanciar objetos con lógica condicional.
	•	Singleton: para instancias únicas como el store.
	•	Observer: para notificaciones tipo pub-sub.
	•	Strategy: para seleccionar algoritmos de forma dinámica.

---

## 5. ¿Cómo garantizas la inmutabilidad del estado en tus aplicaciones?
	•	Usando Object.freeze en objetos.
	•	Evitando mutaciones directas con push, splice, etc.
	•	Usando map, filter, reduce en su lugar.

```js
const nuevoEstado = [...estadoAnterior, nuevoElemento];
```

---

## 6. ¿Qué diferencia hay entre Object.create() y class?
	•	Object.create() crea un objeto con un prototipo especificado.
	•	class es azúcar sintáctico sobre funciones constructoras.

---

## 7. ¿Cómo asegurarías una arquitectura escalable en frontend?
	•	Separación de responsabilidades (componentes, lógica, servicios).
	•	Modularización del código.
	•	Patrones de diseño (como container-presentational).
	•	Uso de TypeScript y tipado estático.
	•	Testing automatizado.

---

## 8. ¿Cómo funciona el modelo de concurrencia en JavaScript?

JS es single-threaded pero usa un modelo asincrónico no bloqueante con Web APIs, Event Loop y colas de tareas.

---

## 9. ¿Cuál es la diferencia entre call, apply y bind?
	•	call: ejecuta la función cambiando el this y pasando args separados.
	•	apply: igual que call pero con args en array.
	•	bind: no ejecuta, devuelve una nueva función con this fijado.

```js
function saluda() {
  console.log(this.nombre);
}
saluda.call({ nombre: 'Ana' });
saluda.apply({ nombre: 'Luis' });
const saludarLuis = saluda.bind({ nombre: 'Luis' });
saludarLuis();
```

---

## 10. ¿Qué son los proxies y para qué sirven?

Permiten interceptar operaciones sobre objetos (get, set, etc.)

```js
const handler = {
  get: (obj, prop) => prop in obj ? obj[prop] : 'No existe'
};
const proxy = new Proxy({ nombre: 'Ana' }, handler);
console.log(proxy.edad); // "No existe"
```

---

## 11. ¿Qué es el currying y cómo lo usarías?

Transforma una función que acepta varios argumentos en una secuencia de funciones que aceptan uno.

```js
const suma = a => b => c => a + b + c;
suma(1)(2)(3); // 6
```

---

## 12. ¿Cómo manejarías múltiples promesas en paralelo?

Usando Promise.all o Promise.allSettled.

```js
const [res1, res2] = await Promise.all([fetch(url1), fetch(url2)]);
```

---

## 13. ¿Qué estrategia usarías para lazy load de módulos?
	•	import() dinámico para carga bajo demanda.
	•	Code splitting con Webpack/Vite.
	•	Suspense y React.lazy (en React).

---

## 14. ¿Qué es un WeakMap y en qué caso lo usarías?

Estructura de datos con claves tipo objeto que no evita el garbage collection. Ideal para almacenar datos privados sin fugas de memoria.

---

## 15. ¿Qué ventajas ofrece TypeScript sobre JavaScript?
	•	Tipado estático en tiempo de desarrollo.
	•	Mejor autocompletado y refactorización.
	•	Prevención de errores comunes.
	•	Integración con editores y CI.

---

## 16. ¿Cómo implementarías control de acceso (roles) en el frontend?
	•	Guardas de rutas (React Router, Angular Guards).
	•	Validación basada en tokens o roles.
	•	HOC o custom hooks según el permiso del usuario.

---

## 17. ¿Qué sabes de Web Workers?

Permiten ejecutar JS en hilos separados sin bloquear el UI thread.

```js
const worker = new Worker('worker.js');
worker.postMessage('Hola');
worker.onmessage = e => console.log(e.data);
```

---

## 18. ¿Qué harías si notas una caída de rendimiento en la app?
	•	Medir con DevTools (timeline, memory).
	•	Revisar renders innecesarios.
	•	Optimizar eventos (debounce, throttle).
	•	Dividir componentes y usar React.memo (si aplica).
	•	Lazy load de módulos pesados.

---

##  19. ¿Cómo aseguras la calidad del código en un equipo?
	•	Linters y formatters (ESLint, Prettier).
	•	PRs con revisiones y comentarios.
	•	Testing automatizado (unit, integration, e2e).
	•	CI/CD y cobertura de pruebas.
	•	Documentación y buenas prácticas.

---

## 20. ¿Cómo asegurarías que una app es accesible?
	•	Usar etiquetas semánticas (<button>, <label>, etc).
	•	Atributos ARIA (aria-label, aria-hidden).
	•	Navegación por teclado.
	•	Contraste adecuado de colores.

---