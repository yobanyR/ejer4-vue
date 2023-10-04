<template>
    <div class="List-person">
      <ListaPersonajes
        v-for="personaje in personajes"
        :key="personaje.nombre"
        :nombre="personaje.nombre"
        :imagen="personaje.imagen"
        :descripcion="personaje.descripcion"
        :personaje="personaje.detalles" 
      />
    
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  import ListaPersonajes from './ListaPersonajes.vue';
  import datos from '@/assets/personajes.json';

  
  
  export default defineComponent({
    name: 'ComponentPersonaje',
    components: {
      ListaPersonajes,
    },
    computed: {
      personajes() {
        return datos.map((personaje: any) => personaje);
      },
    }
  });
  </script>
  
<style lang="scss" scoped>
.List-person {
  margin-top: 50px;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  position: relative;
  z-index: 1; 
}
</style>