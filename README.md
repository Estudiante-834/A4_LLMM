# Enlace al despliegue

https://estudiante-834.github.io/A4_LLMM/  

# Recursos

La actividad ha sido realizada con las etiquetas y propiedades visto en clase, videos individuales grabados por parte del profesor y de los apuntes proporcionados.  

De algunas propiedades utilizadas no vistas en clase son las relacionadas con grid. De estas:

- `display: grid` sirve para cambiar el display del contenedor al que se aplica a grid.
- `gap` para configurar el espaciado entre los elementos flex o grid.
- `grid-template-colum: valor_espaciado` determina como irán los elementos hijos dentro del contenedor grid. Las usada en la actividad separa a los elementos hijos en 3 columnas en espacio iguales.
- `:focus` pseudoclase para aplicar reglas css cuando el elemento en cuestión esté en estado de "enfoque".  

Se ha optado por el uso **propiedades lógicas** en CSS frente al uso de `width` o `height`. Con el `writing mode` normal de izquierda a derecha (ltr), `inline` es `width` (eje x) y `block` es `height` (eye y).  

También se ha optado por añadir `@media` queries o breakpoints dentro de los selectores de elementos en vez de tenerlos fuera por su cuenta. Principalmente debido a la posibilidad de poder hacerlo y por comodidad.  

```
h1 {
    @media (width > 600px) {
        ...
    }
}

vs.

@media (width > 600px) {
    h1 {
        ...
    }
}
```

Se ha optado por utilizar nomenclatura inglesa en la mayor medida posible como recomiendan otros profesores.  

En cuanto a partes del código con mayor dificultad, es la implementación del "sticky footer" o el pie de página que queda "pegado" abajo del todo. Para ello se ha referido a distintos recursos como:

- https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Sticky_footers
- https://www.30secondsofcode.org/css/s/footer-at-the-bottom/

Para ello primero se establece un height de 100% (`block-size: 100%`) en el elemento `body` para que tome el espacio disponible cuando se crea el DOM/CSSOM. Luego se establecen las reglas del `.wrapper` principal de las páginas. Al ser un contenedor flex, los elementos dentro toman el espacio disponible del viewport mediante `min-block-size: 100vh` y se apilan mediante `flex-direction: column`. Por último, cuando añadimos `margin-top: auto` al `footer`, esto fuerza a que consuma solo el mínimo espacio sobrante de su margen superior empujándolo hacia el fondo de la página.
