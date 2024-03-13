<template>
  <!-- no se modifica elcontador suma 1 -->
  <h2>Cena {{ contador + 1 }}
    con el rey godo {{ rey }}</h2>

  <h3 class="precio">Precio: {{ productos[contador].precio }}€</h3>

  <!-- Cuando se cumpla esta condicion -->
  <div v-if="productos[contador].finDeSemana===true" class="soloFinesDeSemana dias">(Solo fines de semana)</div>
  <div v-else class="dias todosLosDias">(De lunes a Domingo)</div>
  
  <div v-if="productos[contador].precio<100" class="oferta">
    <div>Ahorra un 10% dto:
      <!-- Propiedad computada -->
      {{ nuevoPrecio }}€</div>
      <img src="../public/rey_incognito.png" alt="rey godo en descuento" />
    </div>

  <!-- v-bind abreviado -->
  <img :src="imagen" alt="">

  <!-- v-on -->
  <!-- Asi muestra al final total no el numero 7 -->
  <!-- <button @:click="siguiente">Siguiente ({{ contador +1}}/ total)</button> -->
  <button @:click="siguiente">Siguiente ({{ contador +1}}/ {{total}})</button>

</template>

<script setup>

import { ref,computed } from "vue"
import { productos } from './datos.js';
// Importamos valores de archivo desctruturamos para acceder datos
const contador=ref(0)
const total = productos.length;
const ruta = "https://www.html6.es/img/rey_"
const siguiente = () => {
  contador.value++
  if (contador.value >= total) {
    contador.value = 0
  }
}

// Propiedad computada
const rey=computed(()=>{
  // Pongo misnuscula el nombre
  const elNombre=productos[contador.value].nombre.toLowerCase()

  return elNombre.substring(0, 1).toUpperCase() + elNombre.substring(1)
})


  

// Propiedad computada

const imagen = computed(() => {
  // return ruta+productos[contador.value].nombre.toLowerCase()+'.png'
  return `${ruta}${productos[contador.value].nombre.toLowerCase()}.png`
})

const nuevoPrecio = computed(() => {
                                                   //2decimales
  return (productos[contador.value].precio / 1.10).toFixed(2)
})

// import HelloWorld from './components/HelloWorld.vue'
</script>

<style scoped>
.todosLosDias {
  background-color: green;
}

.soloFinesDeSemana {
  background-color: red;
}

.dias {
  color: white;
  padding: 4px 17px;
  font-size: 0.9em;
  border-radius: 4px;
  margin: 5px 0 10px;
  /* Eñ ancho se adaptara al contenido */
  display: inline-block;
}
.oferta img {
  width: 65px;
  margin: 12px 5px;
}

</style>
