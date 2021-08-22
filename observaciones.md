# Observaciones

Elena, felicitaciones por tu trabajo. Me gusta muchísimo como quedó tu portfolio, se nota que acá hay esfuerzo y tiempo invertido. Recorriendolo se ve el esmero que pusiste.

Tengo, lamentablmemente, pocos comentarios para hacerte, ya que el nivel de este trabajo es realmente muy alto. Pero siempre hay algo que comentar! :) Como dije en clase, este trabajo no se hace para que constates conocimientos, sino para que aprendas: en ese sentido, mi intencion es que estos comentarios te sirvan para aprender, mejorar tu codigo a futuro e ir apreciando mejor qué se espera de nosotras como desarrolladoras front end.

Para resolver el formulario noto mucha, demasiada, dependencia del modelo de Ada, incluso en casos donde no tiene sentido con el codigo que ya tenes. El CSS esta muy similar, tenes clases y elementos que no te suman nada, como "form-control". No necesito decirte por qué esto no me impresiona, pero lo más grave es que te deja a vos sin aprender: no se si aprendiste del todo como maquetar vos sola ese formulario, asi que mirar el modelo de Ada en ese caso no sólo no te suma para el TP sino que te roba la oportunidad de aprenderlo. Cuando tengas el tiempo, sin la presión de la entrega encima, te super animo a que trates de hacerlo de cero. 

## Estructura correcta de documento HTML

Tu HTML esta realmente excelente. Claro, prolijo, muy bien comentado e identado.

Algo que me llama la atención es tu `head`, dado que allí repetís innecesariamente el link de devicons. No es necesario escribirlo mas de una vez 

```html
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.9.0/devicon.min.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.9.0/devicon.min.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.9.0/devicon.min.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.9.0/devicon.min.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.9.0/devicon.min.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.9.0/devicon.min.css">
```

Cada uno de esos links hace exactamente lo mismo - traerse el css de devicon para poder usar los iconos en tu sitio. Quizá estés bajo la impresión de que por cada uno de los iconos de tu web es necesario traerse nuevamente el css, pero no, no es necesario agregarlo más de una vez. Agregar muchos de estos links innecesarios impacta negativamente en la velocidad de carga de tu web, ya que por cada uno de ellos se hace un llamado a un css externo y se lo carga. 

Otro detalle es que usas el link de google fonts para CSS. Esto deberia estar en CSS. Si no, tenes que usar el `link` de html que tambien facilita google fonts. No es buena practica poner CSS en html, asi que esto deberia estar en uno de tus archivos de css:

```      
a:link, a:visited, a:active {
        text-decoration:none;
    }
```

Tu `header` deberia ser un `nav`: si bien en algunos diseños identificar el `header` es complejo, creo que en este caso definitivamente debe incluir a la primera sección "introduction-text-container". Un `header` representa siempre lo que llamamos "contenido introductorio": todo aquello que da la bienvenida a nuestra web, sin dar información más específica (pero invitándonos a verla). 

El lenguaje del documento está en inglés, te comento en la sección de accesibilidad por qué eso es importante.

Utilizás ocasionalmente etiquetas `br` para separar las cosas: no llegué a comentarlo en clase, pero esto es incorrecto. Esa etiqueta es un resabio de viejas épocas en las cuales css no era tan poderoso como ahora, pero usarla hoy viola uno de los principios básicos de programación: la separación de responsabilidades. Los estilos se dan con css, la estructura se da con html. Una decisión de estilo como un espaciado entre dos elementos debe controlarse con css -flex, elementos en bloque, etc, no con `br`. 

## Respeta la consigna

- El portfolio cuenta con las secciones solicitadas
- Al clickear en los links de navegación, debe llevar a la sección correspondiente
- Al clickear en los links de contacto, debe llevar a la página externa
  correspondiente
- El portfolio debe tener un diseño responsivo y verse correctamente en distintos dispositivos
- El portfolio debe estar deployado y ser accesible desde una URL
- El repositorio en GitHub debe tener un readme adecuado

Todos estos puntos están cumplidos. Menciono especialmente tu responsive: es increíble lo bien que solucionaste las distintas resoluciones, y las poquisimas media queries que necesitas hablan de que desde el principio tuviste una excelente estrategia para maquetar tu pagina. 

Un comentario es que en las resoluciones de 700 a 550px tu form "rebalsa". Te das cuenta porque hay un scroll horizontal, y una especie de barra blanca que cubre todo el extremo derecho. Esto ocurre normalmente cuando hay un elemento que rebalsa su contenedor, forzando que el body sea más grande que la pantalla. En tu caso, son dos: el margen en la seccion `.sobre-mi`, y el margin y padding de `.contact`. 

Otro comentario es que tenés el mismo problema en celulares, pero optas por tapar el problema con  overflow-x: hidden;. Voy a dejarte encontrar ese elemento como tarea, pero atención a los comentarios del parrafo anterior :) 

### Respeta el diseño dado

El alto de la barra de navegacion es muy grande, yo le quitaria el width ya que no lo necesita. 

Notá que tenes unos margenes alrededor de todo tu sitio: ese es el margen por defecto del body, que deberias eliminar siempre. 

Algunas imágenes no te funcionan: es porque agregaste una / antes de la ruta. Las rutas relativas deberian ser, o bien `src="Images/undraw_wallet_aym5.svg"` o bien `src="./Images/undraw_wallet_aym5.svg" ` (con un punto antes de la /)

### Buena estructura de proyecto

Cumplido, aunque en CSS tan pequeños como este me resulta excesiva la separacion en distintos archivos. Tus carpetas estan capitalizadas: eso atrae errores. Todos los archvos y carpetas deben estar en minuscula. 
Notá que tenés una carpeta innecesaria, `vscode`, que es agregada a veces automáticamente por Visual Studio. Es buena práctica borrarla antes de una entrega. Ojo con las imagenes que tienen mayusculas, es bueno poner todo en minusculas ya que eso atrae problemas al importarlas. 

### Código bien indentado

Tabulas muy bien, lo cual parece un detalle extra cuando una recien comienza pero ayuda un monton a su legibilidad, y que lo hayas logrado en esta etapa es un gran mérito. 

En tu CSS el tabulado está perfecto, pero no dejas el espaciado correcto en cada orden. En lugar de escribir por ejemplo `.name{`, deja un espacio entre el nombre de la clase y la llave: `.name {`

### Comentarios que permiten mejorar la legibilidad del código

Impecables. 

### Uso correcto de etiquetas semánticas

En general usas bien las etiquetas semánticas. Ya te comenté el uso de `header`. Creo también que las tarjetas de producto deberían ser `article` (en este caso, como descendientes directos del `a`). Esto permite que los usuarios de lectores de pantalla los encuentren fácilmente, y también ayuda al SEO. Todo elemento que sea autocontenido, reusable, repetible y pueda usarse en diferentes contextos, debe ser un article. Sobre ese tema te dejo una lectura: https://www.smashingmagazine.com/2020/01/html5-article-section/

Tenés cierta tendencia a tener divs de más. Algunas estructuras de tu web se podrían resolver con menos divs. Dicho esto, yo prefiero que los divs sobren antes de que falten: un div de más se soluciona muy fácil, un div menos puede ser un gran dolor de cabeza cuando estamos recién arrancando. Este sería un comentario que quizá me reservaría para futuros trabajos, pero veo tan bien tu código que me siento confiada en recomendarte que empieces a ver estas cosas desde ya. 

Si tenés ganas, con tiempo, te diría que valdría la pena recorrer tu html y notar que muchas estructuras se pueden hacer más breves eliminando divs que no usas. 

### Buenos nombres de clases

Cumplido. Ocasionalmente tenes clases que no usas, o que dividis en dos sin motivo (por que tus tarjetas de skills tienen la clase skills y icon, por ejemplo? por que usas la clase input-firtsname en html si no la usas en css?). 


### Código CSS bien estructurado

Cumplido. Noto unos pocos estilos innecesarios o confusos, que te voy indicando en tu archivo de css. 

### Reutilización de estilos

Cumplido en general.  Pero ojo, tenes muchisimas clases en tu html que no usas en tu css para nada. 

### Cumple con criterios básicos de accesibilidad

El lenguaje de tu documento de HTML está en inglés, por lo que un lector de pantalla va a tratar de leer todos tus textos en inglés. El efecto es muy feo y confuso: pronuncian en inglés las palabras en español, así que si ven "generador de memes" van a leer "yiniradour di mims". Siempre tratá de que el atributo `lang` de tu HTML refleje el idioma de los textos en tu página.

- Los colores tienen un contraste adecuado

No cumplido siempre que el fondo es #F77DE0 y el texto es blanco. Siempre chequeá con https://webaim.org/resources/contrastchecker/

- Las imágenes tiene el atributo `alt` que corresponde

No cumplido para la imagen principal. El alt quedó vacío. 

- Los íconos y elementos que no presentan texto agregan la información correspondiente por otros medios (etiquetas aria, texto oculto)

Cumplido. 

- Los íconos y elementos que no necesitan ser anunciados por un lector de pantalla tienen la etiqueta aria
  correspondiente

Cumplido 

- Commits con mensajes adecuados

Cumplido, noto muchos y buenos commits en tu proyecto, lo que siempre se agradece.

- Cuenta con un favicon

Cumplido, aunque debería estar en la carpeta principal, en lugar de en la carpeta de imágenes. Muchos servicios de hosting van a buscarlo allí. Tambien deberia llamarse favicon, e idealmente ser de tipo icon en lugar de png. 

### Nota: 8
