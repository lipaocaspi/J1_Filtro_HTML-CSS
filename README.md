# J1_Filtro_HTML-CSS

Para este proyecto se crearon 4 archivos de estilos:

* **productStyle.css** --> hoja de estilos correspondiente al directorio *abrigos*.
* **productStyle1.css** --> hoja de estilos correspondiente al directorio *camiseta*.
* **productStyle2.css** --> hoja de estilos correspondiente al directorio *pantalon*.
* **style.css** --> hoja de estilos correspondiente al archivo principal *index.html* y a los demás archivos html.

**Nota** : la importación de la fuente utilizada se hizo a través de la siguiente línea de código:

```
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;500;600;700&display=swap');
```

## productStyle.css / productStyle1.css / productStyle2.css

Se definen las variables de los colores que se van a usar.

```
:root {
	--grey: #F1F0F6;
	--dark-grey: #8D8D8D;
	--light: #fff;
	--dark: #000;
	--green: #81D43A;
	--light-green: #E3FFCB;
	--blue: #1775F1;
	--light-blue: #D0E4FF;
	--dark-blue: #0C5FCD;
	--red: #FC3B56;
}
```

Se define el elemento como un grid centrado de una sola columna que ocupa el 100 del ancho disponible, color gris claro y un margen y padding.

```
.product {
    display: grid;
    grid-template-columns: 100%;
    align-self: center;
    justify-self: center;
    background-color: #d9d9d9;
    border-radius: 5px;
    border: 2px solid;
    width: fit-content;
    margin: 50px;
    padding: 10px;
}
```

Se define el elemento como un grid centrado horizontalmente.

```
.product__picture {
    display: grid;
    justify-self: center;
}
```

Se define el elemento como un grid con dos columnas y cuatro filas, con un espacio definido entre ellas y un tamaño específico.

```
.product__picture__columns {
    margin: 20px;
    display: grid;
    grid-template-columns: 15% 80%;
    grid-template-rows: repeat(4, 1fr);
    gap: 15px;
    width: 90%;
    height: 80%;
}
```

Las imágenes dentro de *product__picture__columns* ocupan el 100% del elemento, y el cursor cambia.

```
.product__picture__columns img {
    width: 100%;
    height: 100%;
    cursor: pointer;
}
```

A cada una de las imágenes se les asigna un borde.

```
.product__picture__columns__pic1, .product__picture__columns__pic2, .product__picture__columns__pic3, .product__picture__columns__pic4 {
    border: 2px solid;
}
```

Cuando se haga hover en cada imagen de la columna, la imagen más grande cambiará, con una transición de por medio.

```
.product__picture__columns > .product__picture__columns__pic1:hover ~ .product__picture__columns__mainpic_1 {
    background: url('./../images/abrigo1.jpg') no-repeat center;
    transition: all .5s ease;
    background-size: cover;
    width: 100%;
}
```

Se define el fondo de cada imagen grande, con bordes y márgenes específicos.

```
.product__picture__columns__mainpic_1 {
    background: url('./../images/abrigo.jpg') no-repeat center;
    background-size: contain;
    width: 100%;
    padding: 0;
    border: 2px solid;
    margin: 10px;
    grid-column: 2;
    grid-row: 1 / span 4;
}
```

Se definen los detalles del producto como un flex con dirección de columna, centrado horizontalmente y con padding.

```
.product__details {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 10px 25px 10px;
}
```

Se definen las características del botón, como color de fondo, tamaño, padding y color de texto.

```
.button {
    background-color: #3f3e53;
    width: 100px;
    font-size: 1rem;
    padding: 5px 10px 5px 10px;
    border-radius: 5px;
    color: white;
}
```

## style.css

**Nota** : algunos estilos de esta hoja ya han sido explicados anteriormente, por lo que serán omitidos.

Se define el tamaño y el padding de la etiqueta main.

```
main {
	width: 100%;
	padding: 24px 20px 20px 20px;
}
```

Se definen las características del título de main.

```
main .title {
	font-size: 28px;
	font-weight: 600;
	margin-bottom: 10px;
}
```

Se define un grid con columnas que se auto rellenan.

```
main .info-data {
	margin-top: 36px;
	display: grid;
	grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
	grid-gap: 20px;
	overflow: auto;
}
```

Se define una tarjeta definida como flex con dirección de columna, con alineación y sombra.

```
main .info-data .card {
	display: flex;
	flex-direction: column;
	justify-content: end;
	border-radius: 10px;
	height: 350px;
	box-shadow: 4px 4px 16px rgba(0, 0, 0, .05);
}
```

Se define el fondo de la tarjeta.

```
main .one_cat_one {
	background: url('./../images/abrigo.jpg') no-repeat center;
}
```

Se define un pequeño efecto al hacer hover en cada tarjeta.

```
main .card:hover {
	cursor: pointer;
	transform: scale(1.003);
}
```

Se define la cabecera de la tarjeta como un flex con dirección de columna.

```
main .card .head {
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	align-items: center;
}
```

Se definen las caracterísiticas de la cabecera de la tarjeta.

```
main .card .head__picture {
	width: 100%;
	height: 100px;
}
```

Se definen las características de la descripción de la tarjeta, siendo esta un flex con dirección de columna.

```
main .card .head__desc {
	display: flex;
	flex-direction: column;
	padding: 20px;
	border-radius: 10px;
	width: 100%;
	background-color: var(--light-blue);
}
```

Se define que los enlaces de la descripción de la tarjeta no tengan decoraciones.

```
main .card .head__desc__link {
	text-decoration: none;
	color: black;
}
```

Se define la posición del botón de la tarjeta.

```
main .card .head__desc__button {
	display: flex;
	justify-content: space-between;
}
```

Se definen las características del texto del botón de la tarjeta.

```
main .card .head__desc__button__name {
	background-color: #0C5FCD;
	width: 40%;
	padding: 5px;
	border-radius: 5px;
	color: white;
}
```

Se define el tamaño y el grosor de los h2 dentro de la clase *card* y *head*.

```
main .card .head h2 {
	font-size: 24px;
	font-weight: 600;
}
```

Se define el tamaño de los p dentro de la clase *card*.

```
main .card .head p {
	font-size: 14px;
}
```

Se define el tamaño y el grosor de los label dentro de la clase *card*.

```
main .card .label {
	font-size: 14px;
	font-weight: 700;
}
```

Se define que el container sea un grid.

```
.container {
	display: grid;
}
```

Se define que cada item sea un grid con 6 columnas de igual tamaño, alineadas y con bordes y fondos específicos.

```
main .item {
	display: grid;
	grid-template-columns: repeat(6, 1fr);
	justify-content: space-between;
	align-items: center;
	width: 100%;
	padding: 15px;
	margin: 10px 0px 10px 0px;
	border-radius: 15px;
	background-color: var(--light-blue);
	border: 1px solid var(--dark-blue);
}
```

Se define que la imagen de cada item tenga un tamaño específico.

```
main .item__image {
	width: 150px;
}
```

Se define que el texto de cada item esté alineado a la izquierda y sea más grande.

```
main .item__text {
	font-size: larger;
	text-align: left;
}
```

Se define que el ícono de eliminación esté alineado al centro.

```
main .item__delete {
	text-align: center;
}
```

Se define que el footer de la sección sea un flex.

```
main .footer {
	display: flex;
	justify-content: space-between;
}
```

Se define que el botón del footer sea un flex, con un color y borde definido.

```
main .footer__button {
	display: flex;
	justify-content: space-between;
	background-color: #0C5FCD;
	padding: 5px;
	border-radius: 5px;
}
```

Se define que el texto del botón del footer sea un flex centrado y de color blanco.

```
main .footer__button__text {
	display: flex;
	align-items: center;
	color: white;
}
```

Se define que la parte derecha del footer sea un flex, con un color, borde y tamaño definido.

```
main .footer__right {
	display: flex;
	justify-content: space-between;
	align-items: center;
	width: 20%;
	padding: 15px;
	background-color: var(--light-blue);
	border-radius: 10px;
}
```

Se define quqe el texto de la parte derecha del footer sea un flex con dirección de columna.

```
main .footer__right__text {
	display: flex;
	flex-direction: column;
}
```
