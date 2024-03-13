Cena con el Rey Godo: Un festín interactivo con Vue.js

¡Disfruta de una experiencia culinaria única con el Rey Godo!

Este proyecto te permite explorar un menú interactivo de cenas con el Rey Godo. Cada cena tiene un precio y disponibilidad distintos, y puedes navegar por las opciones con un simple clic.

Saborea las características:

    Nombres majestuosos: La primera letra del nombre de la cena se muestra en mayúscula, para un toque de realeza.
    Precios que varían: El precio y la disponibilidad se ajustan según la cena seleccionada.
    Descuentos para plebeyos: Ahorra un 10% en cenas con un precio inferior a 100€.
    Fines de semana de festín: Descubre las cenas disponibles solo en fin de semana.
    Navegación intuitiva: Avanza por el menú con el botón "Siguiente".

Tecnologías:

    Vue.js 3
    Markdown

Requisitos:

    Node.js
    npm o yarn

Preparación:

    Clona el repositorio.
    Instala las dependencias: npm install o yarn.
    Inicia el servidor de desarrollo: npm run serve o yarn serve.
    Dirígete a la URL http://localhost:8080 en tu navegador.

Saborea la demo:

https://www.merriam-webster.com/dictionary/demo

Funciones mágicas:

    Funciones computadas:
        rey: Convierte la primera letra del nombre de la cena en mayúscula.
        imagen: Genera la ruta completa de la imagen de la cena.
        nuevoPrecio: Calcula el precio con un 10% de descuento si es inferior a 100€.
    v-bind: Enlaza propiedades de Vue con atributos HTML.
    v-if: Muestra u oculta elementos según una condición.
    v-else: Muestra un elemento alternativo cuando la condición de v-if es falsa.
    @click: Vincula un evento click a una función.

Un festín de código:
HTML

<h2>Cena {{ contador + 1 }}
  con el rey godo {{ rey }}</h2>

<h3 class="precio">Precio: {{ productos[contador].precio }}€</h3>

<div v-if="productos[contador].finDeSemana===true" class="soloFinesDeSemana dias">(Solo fines de semana)</div>
<div v-else class="dias todosLosDias">(De lunes a Domingo)</div>

<div v-if="productos[contador].precio<100" class="oferta">
  <div>Ahorra un 10% dto:
    {{ nuevoPrecio }}€</div>
    <img src="../public//rey_incognito.png" alt="rey godo en descuento" />
  </div>

<img :src="imagen" alt="">

<button @:click="siguiente">Siguiente ({{ contador +1}}/ {{total}})</button>
Disfruta de este proyecto y úsalo como inspiración para crear tus propias experiencias culinarias con Vue.js.

Recursos adicionales:

    Documentación de Vue.js: https://vuejs.org/
    Guía de Vue.js: https://es.vuejs.org/v2/style-guide/
    Tutoriales de Vue.js: https://vuejs.org/tutorial/

¡Buen provecho!
