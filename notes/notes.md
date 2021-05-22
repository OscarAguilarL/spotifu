<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Curso de Flexbox Layout y Componentes](#curso-de-flexbox-layout-y-componentes)
  - [Convenciones de nombres populares en CSS](#convenciones-de-nombres-populares-en-css)
    - [BEM](#bem)
    - [SuitCSS](#suitcss)
    - [Otras convenciones](#otras-convenciones)
  - [Convenciones para este curso](#convenciones-para-este-curso)
    - [Convenciones generales](#convenciones-generales)
    - [Convenciones CSS](#convenciones-css)
  - [Flexible Box Layout Module](#flexible-box-layout-module)
    - [Flexbox Containers](#flexbox-containers)
  - [Flex Layout Box Model](#flex-layout-box-model)
  - [Orden y dirección](#orden-y-direcci%C3%B3n)
    - [Flex Order](#flex-order)
    - [Flex Direction](#flex-direction)
  - [Flex Lines](#flex-lines)
    - [nowrap](#nowrap)
    - [wrap](#wrap)
    - [wrap-reverse](#wrap-reverse)
  - [Flexibilidad](#flexibilidad)
    - [FLEX-GROW](#flex-grow)
    - [FLEX-SHRINK](#flex-shrink)
    - [FLEX-BASIS](#flex-basis)
    - [FLEX](#flex)
  - [Alineamiento](#alineamiento)
    - [justify-content](#justify-content)
    - [align-items](#align-items)
    - [align-content](#align-content)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

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

## Orden y dirección

### Flex Order

![Flex Order](./img/flex-order.png)

Para lograr el resultado anterior necesitamos tres flex containers:

```html
<div class="flexOrder">
  <img src="./images/grand-escape.jpg" alt="" />
  <p>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum porro ducimus
    minima fuga debitis itaque eligendi quis ea officia odio commodi beatae
    omnis aliquid ratione amet cum, labore nisi minus.
  </p>
</div>
<div class="flexOrder">
  <img src="./images/grand-escape.jpg" alt="" />
  <p>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum porro ducimus
    minima fuga debitis itaque eligendi quis ea officia odio commodi beatae
    omnis aliquid ratione amet cum, labore nisi minus.
  </p>
</div>
<div class="flexOrder">
  <img src="./images/grand-escape.jpg" alt="" />
  <p>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum porro ducimus
    minima fuga debitis itaque eligendi quis ea officia odio commodi beatae
    omnis aliquid ratione amet cum, labore nisi minus.
  </p>
</div>
```

En CSS le daremos un display flex y un gap de 5rem, para el párrafo flex item usaremos una propiedad llamada order, que nos permitira ese efecto de sigzag en los flex items. Como algo adicional daremos un border radius de 50% a las imagenes

```css
.flexOrder {
  display: flex;
  gap: 5rem;
}

.flexOrder:nth-child(even) p {
  border: 1px solid red;
  order: -1;
}

.flexOrder img {
  border-radius: 50%;
}
```

### Flex Direction

La propiedad CSS flex-direction especifica cómo colocar los objetos flexibles en el contenedor flexible definiendo el eje principal y la dirección (normal o al revés)

```css
/* La dirección de los items se presenta en una línea */
flex-direction: row;
```

![row](./img/row.png)

```css
/* Como <row>, pero al revés */
flex-direction: row-reverse;
```

![row-reverse](./img/row-reverse.png)

```css
/* Los items se van apilando */
flex-direction: column;
```

![column](./img/col.png)

```css
/* Como <column> pero al revés */
flex-direction: column-reverse;
```

![column-reverse](./img/col-reverse.png)

## Flex Lines

La propiedad flex-wrap especifica si los flex-items son obligados a permanecer en una misma linea o pueden fluir en varias lineas. Tambien permite controlar la dirección en la cual serán apilados los flex-items

Los valores que puede tomar flex-wrap son:

```css
flex-wrap: nowrap
flex-wrap: wrap
flex-wrap: wrap-reverse
```

### nowrap

Los elementos flex son distribuidos en una sola línea, lo cual puede llevar a que se desborde el contenedor flex.

### wrap

Los elementos flex son colocados en varias líneas.

### wrap-reverse

Actúa como wrap pero cross-start y cross-end están intercambiados.

## Flexibilidad

### FLEX-GROW

Es el factor de crecimiento.
Define la abilidad de crecer de un flex item si es necesario.
Su valor por defecto es 0. NO se aceptan valores negativos

Si todos los items tienen un flex-grow de 1, el espacio sobrante del contenedor será distribuido equitativamente a todos los hijos. Si uno de los hijos tiene un valor de 2, este ocuparía el doble de espacio que los demás.

### FLEX-SHRINK

Factor de reducción.
Este define la habilidad de un elemento flexible de encogerse si es necesario.

Su valor por defecto es 1. NO se aceptan valores negativos

### FLEX-BASIS

Define el tamaño por defecto de un elemento flexible antes de que el espacio restante sea repartido, es en relación a la linea del flex container. Es decir, si la caja tiene flex-direction de row, flex-basis representa el width o inline-size, pero si la caja tiene flex-direction de column, flex-basis representa el height o block-size.

Su valor por defecto es `auto`

### FLEX

Es un shorthand para las ultimas 3 propiedades, se declara en el siguiente orden:

flex-grow | flex-shrin | flex-basis

## Alineamiento

### justify-content

Define la alineación a lo largo del eje principal. Ayuda a distribuir el espacio libre sobrante cuando todos los elementos flexibles de una linea son inflexibles, o son flexibles pero ahan alcanzado su tamaño máximo.

![justify-content](./img/justify-content.png)

### align-items

Define el comportamiento por defecto de la disposición de los elementos flex a lo largo del eje transversal en la línea actual.

![align-items](./img/align-items.png)

### align-content
