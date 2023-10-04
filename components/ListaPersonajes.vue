<template>
  <div class="container mt-4">
    <div class="row">
      <nav class="navbar navbar-dark bg-primary navbar-fixed-top">
        <div class="container-fluid">
          <a class="navbar-brand text-center" href="#">{{ nombre }}</a>
        </div>
      </nav>
      <img :src="require(`@/assets/${imagen}`)" alt="" class="personaje-imagen" />
      <p>{{ descripcion }}</p>
    </div>
    <PostButton class="posicion" :personaje="personaje" /> 
  </div>
</template>


<script lang="ts">
import 'bootstrap/dist/css/bootstrap.css';
import '../assets/css/style.css';
import { defineComponent } from 'vue';
import PostButton from './PostButton.vue';

export default defineComponent({
  name: "ListaPersonaje",
  components: {
    PostButton
  },
  props: {
    nombre: {
      type: String,
      default: ""
    },
    imagen: {
      type: String,
      default: ""
    },
    descripcion: {
      type: String,
      default: ""
    },
    personaje: {
      type: Object,
      default: null
    }
  },
  mounted() {
  console.log('Prop personaje en ListaPersonaje:', this.personaje);
}
  
});
</script>
