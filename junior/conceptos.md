# 🧠 Conceptos clave - Nivel Junior

Este archivo cubre los fundamentos esenciales que todo desarrollador JavaScript junior debe dominar para entrevistas técnicas.

---

## Tipos de Datos

- Primitivos: `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint`.
- Por referencia: `object`, `array`, `function`.

## Conversión de Tipos

- Implícita: `'5' + 1` → `'51'`
- Explícita: `Number('5')` → `5`

## Operadores

- Aritméticos: `+`, `-`, `*`, `/`, `%`
- Comparación: `==`, `===`, `!=`, `!==`, `<`, `>`, etc.
- Lógicos: `&&`, `||`, `!`
- Ternario: `condición ? valor1 : valor2`

## Control de Flujo

- `if`, `else`, `switch`
- `for`, `while`, `do...while`
- `break`, `continue`

## Variables: `var`, `let`, `const`

- `var`: Alcance de función, se puede redeclarar.
- `let`: Alcance de bloque, no se puede redeclarar.
- `const`: Alcance de bloque, no se puede redeclarar ni reasignar.

## Funciones

- Declaración vs Expresión
- Arrow functions
- Parámetros por defecto
- Rest operator (`...args`)

## Arrays y Objetos

- Métodos comunes: `push`, `pop`, `shift`, `unshift`, `slice`, `splice`
- Acceso a propiedades con `.` y `[]`
- Iteración con `for`, `for...of`, `forEach`

## Destructuring

```js
const persona = { nombre: 'Ana', edad: 25 };
const { nombre, edad } = persona;