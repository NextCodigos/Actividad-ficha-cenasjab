<template>
  <!-- no se modifica elcontador suma 1 -->
  <h2>Cena {{ contador + 1 }}
  con el rey godo {{ rey }}</h2>
  
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

// import HelloWorld from './components/HelloWorld.vue'
</script>

<style scoped>

</style>
