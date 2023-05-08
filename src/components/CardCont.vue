<script>
import SingleCard from './SingleCard.vue'
import { store } from '../store';

export default {
  name: "CardCont",
  components: {
    SingleCard,
  },
  data() {
    return {
      store
    }
  },
  methods: {

  }
}
</script>

<template>
  <div class="counter">
    <span class="text-white h6">Found {{ store.yuGiOhCardsData.length }} cards</span>
  </div>
  <main>
    <SingleCard v-for="(element, index) in store.yuGiOhCardsData" :key="index" :dettagliCarta="element" :cindex="index" />
  </main>
</template>

<style lang="scss" scoped>
main {
  height: 100%;
  width: 100%;
  background-color: white;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.counter {
  background-color: black;
  height: 100px;
  width: 100%;
  padding-left: 5%;
  padding-right: 5%;
  display: flex;
  align-items: center;
}
</style>
