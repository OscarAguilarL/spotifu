# Curso de Flexbox Layout y Componentes

Apuntes

## Convenciones de nombres populares en CSS

### BEM

> Block Element Modifier

Bloque: `<ul></ul>`
Elemento: `<li></li>`
Modificador: algun estado especifico del elemento

Ejemplo:

- .block
- .block\_\_element
- .block\_\_fancy-element
- .block\_\_element--modifier

### SuitCSS

Se trabaja con PascalCase en el primer bloque y en el segundo con camelCase.

Ejemplo:

- MyComponent
- MyComponent-part
- myComponent-anotherPart
- myComponent--modifier
- is-state
- u-utility

### Otras convenciones

- BEM
- SuitCSS
- SMACSS
- AtomicCSS

## Convenciones para este curso

### Convenciones generales

- No se escribirán estilos globales a excepción de las configuraciones y theme de la aplicacion.
- Las clases serán basadas en componentes y no se deberán repetir.
- Una hoja de estilos por componente.
- Los componentes no deben tener dependencias externas.
- Los archivos se escribirán kebab-case.

### Convenciones CSS

- .component
- .myComponent
- .myComponent-part
- .myComponent-anothePart
- .is-state

## Flexible Box Layout Module

### Flexbox Containers

- display: flex;
- display: inline-flex;

## Flex Layout Box Model

Hay dos tipos de ejes, eje principal y eje transversal

- El eje principal es la dirección en la que ordenamos nuestros flexibles
