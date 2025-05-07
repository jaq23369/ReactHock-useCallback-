# React Hook: useCallback (Renderizado de Hijos)

## Descripción

Este proyecto demuestra cómo el hook `useCallback` en React puede evitar renderizados innecesarios de componentes hijos cuando se les pasan funciones como props. El ejercicio se ejecuta completamente en un archivo HTML usando React desde CDN y Babel para JSX.

## Objetivos del ejercicio

- Entender cómo una nueva función en cada render puede causar re-render de componentes hijos.
- Usar `useCallback` para memorizar funciones y prevenir renders innecesarios.
- Comparar visualmente el comportamiento de un componente optimizado con `React.memo` y uno no optimizado.

## Estructura del ejercicio

### 1. `Carta`
Componente principal que maneja dos estados:
- `randomNumber`: número aleatorio generado.
- `counter`: contador que se incrementa.

Incluye dos funciones:
- `createRandom`: memorizada con `useCallback`, genera un número aleatorio.
- `addCounter`: no está memorizada, incrementa el contador.

### 2. `ButtonOptimizado`
- Componente hijo memorizado con `React.memo`.
- Recibe `createRandom` como prop.
- Solo se re-renderiza si la función cambia.

### 3. `ButtonNormal`
- Componente hijo sin `memo`.
- Recibe `addCounter`, que cambia en cada render.
- Se re-renderiza cada vez que `Carta` se actualiza.

## Comportamiento observable

- Al hacer clic en "Generar Número Aleatorio", `ButtonOptimizado` **no se re-renderiza**.
- Pero `ButtonNormal` **sí se re-renderiza siempre**, incluso si no fue invocado, porque su función cambia cada vez.
- Los `console.log()` en consola muestran claramente qué botón se renderiza y cuándo.

## Tecnologías utilizadas

- React 18 (CDN)
- ReactDOM 18 (CDN)
- Babel (para permitir JSX en el navegador)

## Como correr el ejercicio

-Clonando el repositorio y ejecutando el index.html con liveServer
-Accediendo desde la siguiente ruta que lleva al servidor de la clase: http://awita.site/usuarios/jaq23369/React%20Hook%20%28UseCallBack%29%20CDN/






