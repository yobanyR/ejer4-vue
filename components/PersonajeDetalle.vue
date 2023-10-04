<template>
    <div class="post-container">
      <h2>Detalles del Personaje</h2>
      <p>Habilidad: {{ personaje.habilidad }}</p>
      <p>Poder: {{ personaje.poder }}</p>
      <p>Tribu: {{ personaje.tribu }}</p>
    </div>
</template>
  
<script lang="ts">
  import { defineComponent } from 'vue';
  
  interface Personaje {
    habilidad: string;
    poder: string;
    tribu: string;
  }
  
  export default defineComponent({
    props: {
      personaje: {
        type: Object as () => Personaje,
        required: true,
      },
    },
  });
</script>
  
  

<style lang="scss" scoped>
    .post-container {
        width: 100%;
        display: flex;
        flex-wrap: wrap;
    }
</style>