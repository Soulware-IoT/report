Con el objetivo de mantener un código ordenado, consistente y fácil de mantener entre todos los miembros del equipo, se han definido las siguientes convenciones. Todas las variables, funciones, clases, archivos y elementos estarán en inglés.

- Se utilizará **inglés** como idioma único para nombres de variables, funciones, clases, comentarios y documentación.
- Se evitarán abreviaciones innecesarias y nombres genéricos como `data1`, `temp`, `info`, etc.

**HTML**
Atributos en minúsculas y nombres de clase con **kebab-case** (`section-title`, `main-container`).
- Estructura semántica clara: uso de etiquetas como `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`.
- Sangría con 2 espacios.
- Atributos ordenados de manera lógica: `id`, `class`, `type`, `name`, `placeholder`, `value`, `required`, etc.

**CSS**

- Para clases personalizadas: usar **kebab-case**.
- Se agruparán clases de utilidad por orden lógico (layout -> spacing -> color -> typography).

**Google TypeScript Style Guide**

Basado en el [Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html), se adoptan las siguientes reglas para mantener un código limpio y coherente:

Nombres y sintaxis:
- **camelCase** para variables, funciones y parámetros.
- **PascalCase** para clases, interfaces, enums y tipos.
- Constantes con `UPPER_CASE_WITH_UNDERSCORES` si son globales.

Módulos y imports:
- Preferir **imports explícitos y ordenados**: primero bibliotecas externas, luego internas.
- Evitar `default exports`, usar siempre `export const` o `export class`.

Tipado y declaraciones:
- Siempre tipar explícitamente los parámetros y valores de retorno de funciones.
- Evitar `any` excepto cuando sea estrictamente necesario.
- Usar `readonly` para propiedades que no deben cambiarse.
- Interfaces en lugar de `type` cuando sea posible.

Buenas prácticas:
- Preferir `const` sobre `let`, y evitar `var`.
- Evitar usar `this` fuera de clases.
- No mezclar funciones y lógica en componentes — delegar a servicios.

**Vue.js**

- Seguir la [Vue 3 Style Guide (Oficial)](https://vuejs.org/style-guide/), especialmente las reglas **“Essentials”** y **“Strongly Recommended”**.
- Componentes deben nombrarse en **PascalCase** (`UserCard.vue`, `HeroSection.vue`).
- Archivos `.vue` deben tener una única raíz (`<template>`, `<script>`, `<style>`).
- Uso claro de `v-bind`, `v-model`, `v-if`.
- Eventos deben seguir `kebab-case` en los templates (`@form-submitted`).
- Evitar lógica compleja dentro de los templates.
- Separar componentes base (`BaseButton`, `BaseInput`) de componentes de dominio.