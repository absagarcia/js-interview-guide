# 🧠 Conceptos clave - Nivel Senior

Este documento cubre conocimientos avanzados que todo desarrollador JavaScript senior debe dominar, especialmente en entrevistas técnicas, revisión de código y liderazgo técnico.

---

## ⚙️ Memory Management

- Entender cómo funciona el Garbage Collector.
- Detección y prevención de **memory leaks** (referencias no liberadas).
- Uso de `WeakMap` y `WeakSet` para colecciones sin retención de memoria.

---

## 🔁 Debounce y Throttle

Técnicas de optimización para controlar la ejecución de funciones en eventos de alta frecuencia.

- **Debounce**: espera a que deje de ejecutarse.
- **Throttle**: ejecuta cada cierto tiempo máximo.

---

## 🔥 Performance Optimization

- Minimizar repintados del DOM.
- Técnicas de lazy loading, virtual DOM, memoization.
- Uso de `requestAnimationFrame` para animaciones.

---

## 🧭 Deep Dive en el Event Loop

- Diferencias exactas entre **microtasks** y **macrotasks**.
- Comprender fases del loop: poll, check, timers.

---

## 🧱 Principios SOLID en JavaScript

1. **Single Responsibility**
2. **Open/Closed**
3. **Liskov Substitution**
4. **Interface Segregation**
5. **Dependency Inversion**

Aplicarlos en clases, módulos y funciones.

---

## 🧠 Patrones de diseño en JavaScript

- Singleton
- Factory
- Observer
- Module
- Strategy
- Decorator

---

## 🗂️ Arquitecturas modernas

- Arquitectura basada en componentes.
- Arquitectura hexagonal o “clean architecture”.
- State management patterns (Redux, Context, Zustand, etc).

---

## 🔒 Seguridad en JavaScript

- XSS (Cross Site Scripting)
- CSRF (Cross Site Request Forgery)
- Sanitización de datos del usuario
- Uso de `Content Security Policy (CSP)`

---

## ⚠️ Errores comunes y debugging

- Manejo adecuado de errores con `try/catch`.
- Uso de `Error boundaries` en React.
- Uso avanzado de DevTools, breakpoints, performance tab, memory profiling.

---

## ⚙️ Testing avanzado

- Testing de componentes UI con mocks/stubs.
- Cobertura de código.
- Testing de integración y end-to-end (Jest, Cypress, Playwright).

---

## 🧩 Inmutabilidad y programación funcional

- Usar `map`, `reduce`, `filter` de forma pura.
- No mutar estado original (inmutabilidad).
- Composición de funciones.

---

## 🧵 Multithreading y Web Workers

- Cómo delegar tareas pesadas a Web Workers.
- Uso de `postMessage` y `onmessage`.

---

## 📦 Bundlers y Transpilers

- Diferencias entre Webpack, Rollup, Vite.
- Uso de Babel para transpilación ES6+.

---

## 🧪 Tipado con TypeScript

- Tipos básicos y avanzados.
- Tipos genéricos.
- Interfaces y utility types.
- Inferencia de tipos y seguridad en tiempo de compilación.

---

## ⛓️ Prototype chain y herencia

- `Object.prototype`
- `__proto__`, `Object.getPrototypeOf()`
- Herencia prototípica vs clases modernas (`class`, `extends`)

---

## 🧱 Clases vs Funciones constructoras

```js
class Persona {
  constructor(nombre) {
    this.nombre = nombre;
  }
  saludar() {
    return `Hola, soy ${this.nombre}`;
  }
}
```

---

## 🔄 Async Generators y for await...of

Permiten manejar flujos asincrónicos con múltiples valores.

```js
async function* generador() {
  yield await Promise.resolve(1);
  yield await Promise.resolve(2);
}
for await (const valor of generador()) {
  console.log(valor);
}
```

---

## 🔐 Autenticación y autorización en frontend
	•	JWT (JSON Web Tokens)
	•	OAuth2 / OpenID Connect
	•	Guardas de ruta y roles de usuario
	•	Expiración de tokens y renovación silenciosa

---

## 🌍 Internacionalización (i18n) y Accesibilidad (a11y)
	•	Uso de librerías como i18next.
	•	Buenas prácticas para accesibilidad: aria-*, etiquetas semánticas, navegación por teclado.

---

## 🧠 Reflexión
	•	Object.keys, Object.values, Object.entries
	•	Acceso dinámico a propiedades con []
	•	Métodos hasOwnProperty, in