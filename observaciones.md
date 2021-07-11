# Observaciones

Chari, lo primero es felicitarte por un hermoso trabajo. Tu portfolio se ve muy lindo; me alegra ver que en general seguiste las pautas del diseño solicitado pero a la vez le diste tu toque personal. Se nota, y aprecia, que hubo mucho trabajo para lograr una web que te represente y que sea amable con el usuario.

Noto algún apego a varias estructuras del HTML y CSS del modelo de Ada, incluso en situaciones donde no tiene sentido. Por darte un ejemplo, que no es el único que vi, tus iconos del footer tienen la clase "footer-social-icon". En el modelo de Ada esa clase tiene sentido, ya que agrega estilos. En el tuyo está completamente de más.
Por supuesto, el codigo de esa web es público y sabemos y comprendemos que ocasionalmente vas a mirarlo para despejar algunas dudas. Sólo vos podés saber cuánto fue resolución de dudas y cuánto fue "inspiración" un poco más problemática, yo solo puedo sospechar, pero no es algo que te recomiende hacer. Algunos problemas parecen obvios de solucionar cuando ves como lo hace el modelo, pero esa no es la única manera, ni la mejor. La mejor, por supuesto, es la que se te ocurra a vos. Prefiero que me entregues un código incompleto si no llegas con el tiempo: hace que perdamos menos tiempo ambas y me da una idea más realista de lo que podés hacer. 

Te dejo varios comentarios para mencionar cositas puntuales. Como comentamos en clase, este trabajo no se hace para que constates conocimientos, sino para que aprendas: en ese sentido, mi intencion es que estos comentarios te sirvan para aprender, mejorar tu codigo a futuro e ir apreciando mejor qué se espera de nosotras como desarrolladoras front end.

## Estructura correcta de documento HTML

Tu HTML esta realmente excelente. Claro, prolijo, muy bien comentado. 

Algunas decisiones no están bien. Importás las tipografías de google usando el comando para css, por lo que tenés que agregar innecesariamente una etiqueta `style` en el header. Eso debería estar directamente en el css, o deberías usar los `link` para html que Google Fonts te da. El lenguaje del documento está en inglés, te comento en la sección de accesibilidad por qué eso es importante.

Tenés cierta tendencia a tener divs de más. Algunas estructuras de tu web se podrían resolver con menos divs. Dicho esto, yo prefiero que los divs sobren antes de que falten: un div de más se soluciona muy fácil, un div menos puede ser un gran dolor de cabeza cuando estamos recién arrancando. Pero está bueno que desde ahora vayas notando esas cosas. Tomá por ejemplo el div que es padre directo de de la etiqueta `nav`. Hace algo? Pasa algo si lo sacás?


## Respeta la consigna 

- El portfolio cuenta con las secciones solicitadas 
- Al clickear en los links de navegación, debe llevar a la sección correspondiente
- Al clickear en los links de contacto, debe llevar a la página externa
correspondiente 
- El portfolio debe tener un diseño responsivo y verse correctamente en distintos dispositivos 
- El portfolio debe estar deployado y ser accesible desde una URL 
- El repositorio en GitHub debe tener un readme adecuado 

Todos estos puntos están cumplidos. El Readme es buenisimo! 

Con respecto al responsive, funciona a la perfeccion en escritorio y celulares, mas no en tablets o escritorios chicos. Voy a considerarlo cumplido, porque atacaste las dos resoluciones mas importantes, pero estaria buenisimo que puedas lograr que tu web se vea igual de increible en todas las resoluciones. Creo que comenté en clase que lo más habitual es seguir las media queries que sugiere bootstrap. Te las dejo como una guia para futuros trabajos:

```css
/* Celulares: hasta 320px debería verse bien */
@media (max-width: 576px) {
  ...;
}

/* Celulares en modo horizontal y tablets pequeñas */
@media (max-width: 768px) {
  ...;
}

/* Tablets  */
@media (max-width: 992px) {
  ...;
}

/* Monitores pequeños */
@media (max-width: 1200px) {
  ...;
}

/* Monitores grandes */
@media (max-width: 1400px) {
  ...;
}
```


### Respeta el diseño dado 

Cumplido; todos los textos, imagenes, etc, se ven un poco más grandes en tu web que en el modelo. Voy a considerarlo una preferencia, pero tené en cuenta que para el mundo laboral o para un challenge de una empresa, es importante que sigas esas medidas fielmente. 

### Buena estructura de proyecto 

En general, cumplido. Tu carpeta de imagenes tiene una mayúscula en el título, algo que podría traerte problemas en el linkeado. Nunca ni tus archivos, ni nombres de carpetas, ni nombres de clases, deberian tener mayusculas: trae un monton de problemas. 

### Código bien indentado 

Tabulas muy bien en general, lo cual parece un detalle extra cuando una recien comienza pero ayuda un monton a su legibilidad, y que lo hayas logrado en esta etapa es un gran mérito. Ocasionalmente tenés comprensibles ausencias de tabulado, que espero que con el tiempo vayas detectando y mejorando, como aquí:

```html
  <footer>
    <div class="footerorg">
    <!--Navegacion Footer-->
    <nav class="footernav">
    <ul class="footernavmenu">
    <li class="footernavitem">
```

Como cada uno de esos elementos está contenido dentro del anterior, la manera correcta de tabularlo sería esta:

```html
  <footer>
    <div class="footerorg">
      <!--Navegacion Footer-->
      <nav class="footernav">
        <ul class="footernavmenu">
          <li class="footernavitem">
``` 

En tu CSS el tabulado está perfecto, pero no dejas el espaciado correcto entre cada orden. Corresponde un salto de linea entre cada uno:

```css
  .inputfirstname {
    width: 100%;
  }
  .inputsurname {
    width: 100%;
  }
  .formemail {
    width: 100%;
  }
```

### Comentarios que permiten mejorar la legibilidad del código 

Impecables. 

### Uso correcto de etiquetas semánticas 

Cumplido a medias. Comentamos en clase que el `header` no era exclusivamente el `nav`, así que no deberías haberlo usado acá. Tus tarjetas, tanto las de proyectos como las de tecnologías, deberían ser `article`, en tu caso no usan ninguna etiqueta semántica. Los iconos con links al final del footer bien podrían haber sido un `ul`.

### Buenos nombres de clases 

No lo considero cumplido del todo. Insisto en que no uses mayúsculas en HTML: abundan en tus nombres de clases. Para separar palabras, privilegiá usar guiones: "header-style" en lugar de "headerStyle". 

Muchas veces tus nombres de clases no son descriptivos en sentido funcional. Idealmente, debería poder leer el CSS sin ir a mirar el HTML, porque tus nombres de clases me indicarían claramente qué es cada cosa. En tu TP tuve que hacerlo muchas veces. Tomá por ejemplo esta serie de nombres: projects, projectscontent, projectsflex, projectbox. Es muy difícil saber qué es cada cosa. "Seccion proyectos", "Contenido proyectos", "contenedor tarjetas proyectos" y "tarjetas proyectos" son nombres mucho más claros. 

### Código CSS bien estructurado 

Cumplido a nivel formal. Noto muchos estilos innecesarios o confusos, que te voy indicando en tu archivo de css. 

### Reutilización de estilos 

Cumplido

### Cumple con criterios básicos de accesibilidad 

El lenguaje de tu documento de HTML está en inglés, por lo que un lector de pantalla va a tratar de leer todos tus textos en inglés. El efecto es muy feo y confuso: pronuncian en inglés las palabras en español, así que si ven "generador de memes" van a leer "yiniradour di mims". Siempre tratá de que el atributo `lang` de tu HTML refleje el idioma de los textos en tu página.

Eliminas el outline en el formulario, por lo que ese formulario no se puede recorrer con el teclado. Nunca nunca nunca elimines el outline a menos que lo reemplaces con otra cosa. 

- Los colores tienen un contraste adecuado 

No cumplido en tus botones, siempre que tenes el color de fondo #20B2AA (light sea green) con texto blanco. Controlá el contraste siempre con herramientas del tipo https://webaim.org/resources/contrastchecker/

- Las imágenes tiene el atributo `alt` que corresponde 

Tenes dos alt nada mas, los dos en ingles, cuando el lenguaje de tu pagina es en español, y uno ilegible para un lector de pantalla ("portfoliophoto": recorda que el lector lee palabras bien escritas, ahi va a tratar de leerlo foneticamente porque no va a encontrar esa palabra en el diccionario). 

- Los íconos y elementos que no presentan texto agregan la información correspondiente por otros medios (etiquetas aria, texto oculto) 

No cumplido, por ejemplo en los links a redes sociales de tu footer. Necesitan un aria. 

- Los íconos y elementos que no necesitan ser anunciados por un lector de pantalla tienen la etiqueta aria
correspondiente 

Cumplido. 

- Commits con mensajes adecuados 

Cumplido, noto muchos y buenos commits en tu proyecto, lo que siempre se agradece. 

- Cuenta con un favicon

No cumplido. 

### Nota: 8