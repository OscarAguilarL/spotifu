# Curso de Flexbox Layout y Componentes

Apuntes

## Convenciones de nombres populares en CSS
### BEM
> Block Element Modifier

Bloque: `<ul></ul>`
Elemento: `<li></li>`
Modificador: algun estado especifico del elemento

Ejemplo:
* .block
* .block__element
* .block__fancy-element
* .block__element--modifier

### SuitCSS
Se trabaja con PascalCase en el primer bloque y en el segundo con camelCase.

Ejemplo:
* MyComponent
* MyComponent-part
* myComponent-anotherPart
* myComponent--modifier
* is-state
* u-utility

### Otras convenciones
- BEM
- SuitCSS
- SMACSS
- AtomicCSS

## Convenciones para este curso
### Convenciones generales
* No se escribirán estilos globales a excepción de las configuraciones y theme de la aplicacion.
* Las clases serán basadas en componentes y no se deberán repetir.
* Una hoja de estilos por componente.
* Los componentes no deben tener dependencias externas.
* Los archivos se escribirán kebab-case.

### Convenciones CSS
* .component
* .myComponent
* .myComponent-part
* .myComponent-anothePart
* .is-state