# Plan de ataque: Corrección y validación del juego "Adivina tu número"

Este documento detalla las correcciones realizadas al código del juego desarrollado en JavaScript que permite al usuario adivinar un número del 1 al 100. Se revisaron errores de lógica, sintaxis, y se integró una validación de entrada sólida. El propósito es garantizar alineación con las reglas del negocio y mejorar la experiencia del usuario.

---

## Objetivo del juego

Permitir al usuario adivinar un número entero entre 1 y 100 en un máximo de 10 intentos. El sistema ofrece pistas (“mayor” o “menor”) y gestiona la finalización del juego de forma dinámica.

---

## Correcciones aplicadas

### 1. Generación del número aleatorio

- **Antes**: `Math.random() * 10`
- **Ahora**: `Math.floor(Math.random() * 100) + 1`
- **Justificación**: genera un número entero entre 1 y 100, cumpliendo con la lógica del juego.

---

### 2. Ajuste del número de intentos

- **Antes**: `const ATTEMPS = 5`
- **Ahora**: `const ATTEMPS = 10`
- **Justificación**: según la instrucción del juego, se permiten hasta 10 intentos.

---

### 3. Corrección de selectores del DOM

- **Error**: `querySelector('lowOrHi')`
- **Corregido**: `querySelector('.lowOrHi')`
- **Justificación**: se requiere el prefijo `.` para seleccionar por clase en CSS.

---

### 4. Conversión de tipos en comparaciones

- **Antes**: comparación directa entre `string` y `number`
- **Ahora**: conversión explícita con `Number(userGuess)`
- **Justificación**: evita errores por coerción implícita en JavaScript, mejorando la precisión de las comparaciones.

---

### 5. Validación de entrada

```js
if (!Number.isInteger(userGuess) || userGuess < 1 || userGuess > 100)

```
- Justificación: asegura que solo se acepten números enteros positivos entre 1 y 100. Evita valores fuera de rango, decimales o cadenas no numéricas.

---

## Corrección de eventos
- **Error tipográfico**: `addeventListener` (incorrecto)
- **Corregido**: `addEventListener` (correcto)
- Justificación: Mayúsculas incorrectas no permitían la ejecución de eventos.

---

## Mejoras en la experiencia del usuario
- Mensajes claros en caso de victoria, derrota y error de entrada.
- Foco automático en el campo de entrada para facilitar la interacción.
- Limpieza del campo tras cada intento.
- Posibilidad de reiniciar el juego dinámicamente.

---

## Posibles mejoras futuras
- Mostrar intentos restantes en cada jugada.
- Añadir sonido o animación al ganar o perder.
- Adaptar el diseño para dispositivos móviles.
- Internacionalización del texto (multi-idioma).

---

## Conclusión
Estas correcciones mejoran la lógica del juego, aseguran que cumpla con los requerimientos funcionales, y fortalecen la robustez del código. El resultado es una base limpia, confiable y preparada para escalar.

