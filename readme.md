
# Guía CSS, SASS y Conceptos Relacionados

## CSS Plano (Desventajas)
El **CSS plano** es el uso directo de CSS sin preprocesadores ni herramientas adicionales. Aunque es suficiente para proyectos pequeños, tiene varias limitaciones que hacen que sea menos eficiente para proyectos más grandes o complejos.

### Desventajas:
- **Difícil de mantener** en proyectos grandes, ya que no permite la reutilización de valores o reglas de manera eficiente.
- **Falta de modularidad**, ya que todo el CSS suele colocarse en un único archivo o en pocos archivos grandes.
- **No soporta variables** para reutilización de colores, fuentes o tamaños, lo que obliga a repetir valores.
- **Anidamiento limitado**, lo que lleva a una estructura menos clara y más repetición de selectores.

### Ejemplo:
```css
.menu {
  background-color: blue;
}

.menu-item {
  color: white;
}
```

## ¿Qué es un Procesador?
En el contexto de CSS, un **procesador** o **preprocesador** es una herramienta que extiende las capacidades de CSS añadiendo características como variables, funciones, mixins, anidamiento de selectores, entre otros. El código que escribes con un preprocesador es más dinámico y fácil de mantener, y luego se compila a CSS estándar que puede ser leído por los navegadores.

### Ejemplo:
```scss
$color-principal: blue;

.menu {
  background-color: $color-principal;
}
```

## SASS (Ventajas)
**SASS**  es un preprocesador de CSS que añade nuevas funcionalidades que facilitan la escritura de hojas de estilo más organizadas, modulares y eficientes. Ofrece características como variables, anidamiento, mixins, funciones, y permite dividir el código en múltiples archivos (modularidad).

### Ventajas:
- **Variables**: Reutiliza valores a lo largo del proyecto.
- **Anidamiento de selectores**: Mejora la legibilidad del código y reduce la repetición de selectores.
- **Modularidad**: Permite dividir los estilos en varios archivos y luego combinarlos.
- **Mixins y funciones**: Permiten crear estilos reutilizables y aplicar lógica en CSS.

### Ejemplo:
```scss
$color-principal: blue;

.menu {
  background-color: $color-principal;

  .item {
    color: white;
  }
}
```

## Variables
Las **variables** en SASS permiten almacenar valores como colores, fuentes o tamaños para reutilizarlos en varias partes del código. Esto facilita el mantenimiento, ya que solo necesitas cambiar el valor en un lugar para que se actualice en todo el proyecto.

### Ejemplo:
```scss
$color-fondo: #f0f0f0;

body {
  background-color: $color-fondo;
}
```

## Anidamiento (Selectores)
El **anidamiento** en SASS permite escribir selectores de una forma jerárquica, lo que facilita la legibilidad y reduce la repetición de selectores. Puedes anidar selectores hijos dentro de los selectores padres para reflejar mejor la estructura del HTML.

### Ejemplo:
```scss
.menu {
  background-color: blue;

  .item {
    color: white;
  }
}
```

## Anidamiento con Ampersand (`&`)
El símbolo **`&`** en SASS hace referencia al selector padre dentro del cual se está utilizando. Es útil cuando necesitas referirte al selector padre en pseudo-clases o combinaciones más complejas de selectores.

### Ejemplo:
```scss
.boton {
  color: blue;

  &:hover {
    color: green; /* Cambia el color cuando se hace hover sobre el botón */
  }
}
```

## Importación (Modularidad, `@import`, Parciales)
**SASS** permite la **modularidad** mediante la **importación** de archivos parciales, lo que significa que puedes dividir tu CSS en múltiples archivos más pequeños (denominados **parciales**), y luego importarlos en un archivo principal. Los parciales se identifican por un guion bajo (`_`) en su nombre y no se compilan directamente, solo se importan.

### Ejemplo:
Archivo `_variables.scss` (parcial):
```scss
$color-principal: blue;
```

Archivo `style.scss`:
```scss
@import 'variables';

.menu {
  background-color: $color-principal;
}
```
