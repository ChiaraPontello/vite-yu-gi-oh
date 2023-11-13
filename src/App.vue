<template>
  <!--HEADERCOMPONENT-->
  <HeaderComponent />
  <!-- MAINCOMPONENT -->
  <main>
    <div class="container">
      <div class="row">
        <div class="col-3 " v-for="item in store.cardsList" :key="item.id">
          <MainComponent :image="item.card_images[0].image_url" :name="item.name" :archetype="item.archetype" />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import axios from 'axios';
import { store } from './data/store.js'
export default {
  name: "App",
  components: {
    HeaderComponent,
    MainComponent,
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCards() {
      axios.get(store.apiUrl).then((response) => {
        store.cardsList = response.data.data
      })
    }
  },
  created() {
    this.getCards()
  }
}
</script>

<style lang="scss" scoped>

</style>