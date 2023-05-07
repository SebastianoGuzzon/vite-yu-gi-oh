<template>
  <main class="p-5">
    <div class="container p-5 bg-white rounded-4">
      <div class="row gap-4 d-flex justify-content-center">
        <div v-for="card in store.cardElements" class="col-12 col-sm-6 col-md-4 col-lg-2">
          <div class="card">
            <img :src="card.card_images[0].image_url" :alt="card.name">
            <div class="card-body dc-card-body text-center">
              <h5 class="text-white">Nome:</h5>
              <h5 class="text-white">{{ card.name }}</h5>
              <span class="pt-4 fw-bold" v-if="card.archetype">Archetype:</span>
              <p>{{ card.archetype }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import { store } from '../data/store';
export default {
  name: 'MainComponent',
  data() {
    return {
      store
    }
  },
};
</script>

<style lang="scss" scoped>
main {
  background-color: #048f7c;
}

.dc-card-body {
  min-height: 184px;
  max-height: 184px;
  background-color: #d48f38;
}
</style>