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
