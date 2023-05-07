<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import axios from 'axios'
import { store } from './data/store';
export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent
  },
  data() {
    return {
      store
    }
  },

  // -Al caricamento della pagina, effettuate una chiama ajax all’API di Vite Yu Gi Oh
  // Documentazione: https://ygoprodeck.com/api-guide/

  methods: {
    getElements() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=').then((el) => {
        console.log(el.data.data[0]);
        store.cardElements = el.data.data;
      });
    }
  },
  mounted() {
    this.getElements();
  }
}
</script>

<template>
  <HeaderComponent />
  <MainComponent />
</template>


<style scoped></style>