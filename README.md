IDAT_CSS

**Especificidad:** es la forma mediante la cual los navegadores reconocen qué valores de una propiedad CSS son más relevantes para un elemento.
De menor a mayor estarían ordenados de la siguiente manera:

- (asterisco) Selector universal = 0
- (tags) Etiquetas = 1
- (.) Clases = 10
- (#) ID = 100
- (style) InLine = 1000
- !important = 10000

  - Ejemplo:

  ```
  <h1 class="title" id="titulo" style="color:green">CSS</h1>
  ```

  En la hoja styles.css:

```
  * {
  color: brown;
  }

  h1 {
  color: blue;
  }

  .title {
  color: orange !important;
  }

  #titulo {
  color: red;
  }
```

En este ejemplo el texto se mostrará "naranja", porque lleva el atributo "!important", en caso no esté esto se mostraría de color verde, de forma similar luego sería rojo, seguido naranja, azul y finalmente marrón en caso todos los demás no estén. En conclusión se cumple la jerarquía: !important > inline > #id > .clase > etiqueta > asterisco.

**Recomendación:** evitar el uso de !important, salvo se necesite en declaraciones específicas de CSS que sobrescriban CSS externo.

_Fuente:_ (https://developer.mozilla.org/es/docs/Web/CSS/Specificity)

**Selectores:** definen sobre qué elementos se aplicará un conjunto de reglas CSS.
Según la MDN se tienen los siguientes selectores:

- Selector de tipo: sintaxis (eltname)

  - Ejemplo: "input" se aplicará a cualquier elemento <input>.

- Selector de clase: sintaxis (.classname)

  - Ejemplo: ".index" seleccionará cualquier elemento que tenga la clase "index".

- Selector de ID: sintaxis (#idname)

  - Ejemplo: "#toc" se aplicará a cualquier elemento que tenga el ID "toc".

- Selector universal: sintaxis (asterisco)

  - Ejemplo: "asterisco" se aplicará a todos los elementos del documento.

- Selector de atributo: sintaxis ([attr] [attr=value] [attr~=value] [attr|=value] [attr^=value] [attr$=value] [attr*=value])

  - Ejemplo: [autoplay] seleccionará todos los elementos que tengan el atributo "autoplay" establecido (a cualquier valor).

  _Fuente:_ (https://developer.mozilla.org/es/docs/Web/CSS/CSS_Selectors)

**Cascada:** se aplica cuando dos reglas tienen la misma especificidad, se aplica la que aparece en último lugar en el CSS.

- Ejemplo: a continuación se muestra dos selectores de etiqueta "h1" con el atributo color distinto en cada uno, el resultado será azul porque es la última que aparece.
  ```
  h1 {
  color: red;
  }
  h1 {
  color: blue;
  }
  ```

**Herencia:** algunos valores de las propiedades CSS que se han establecido para los elementos padre los heredan los elementos hijo, pero otros no.

- Ejemplo: si para un elemento se establece el color (color) y el tipo de letra (font-family), cada elemento que se encuentre dentro de él también se mostrará de ese color y con ese tipo de letra, salvo se haya aplicado un color y un tipo de letra diferentes directamente.

**Observación**: Algunas propiedades no se heredan. Por ejemplo, si para un elemento se establece un ancho width del 50%, sus descendientes no tendrán un 50% de ancho con respecto al de sus padres. Si este fuera el caso, ¡sería muy frustrante usar CSS!

_Fuente:_ (https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance)
