<template>
  <div>
    <button class="post-button" @click="mostrarDetalle = !mostrarDetalle">
      {{ mostrarDetalle ? 'Ocultar Detalle' : 'Mostrar Detalle' }}
    </button>
    <!-- Mostrar el detalle solo si mostrarDetalle es verdadero y personaje está definido -->
    <div v-if="mostrarDetalle && personaje">
      <h4>Detalles del Personaje</h4>
      <p v-if="personaje.habilidad">Habilidad: {{ personaje.habilidad }}</p>
      <p v-if="personaje.poder">Poder: {{ personaje.poder }}</p>
      <p v-if="personaje.tribu">Tribu: {{ personaje.tribu }}</p>
    </div>
  </div>
</template>



<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: "PostButton",
  props: {
    personaje: Object // Asegúrate de que el nombre de la prop sea 'personaje'
  },
  data() {
    return {
      mostrarDetalle: false
    };
  },
  methods: {
    toggleDetalle() {
      this.mostrarDetalle = !this.mostrarDetalle;
    }
  },
  mounted() {
  console.log('Prop personaje en boton:', this.personaje);
}
});
</script>

<style lang="scss" scoped>
.post-button {
  background-color: aqua;
  padding: 3px;
  border: solid 1px blue;
  
  &:hover {
    background-color: blue;
    border: solid 1px aqua;
    color: #FFFFFF;
  }
  
  margin-bottom: 0%;
}

p {
  text-align: left;
}
</style>
