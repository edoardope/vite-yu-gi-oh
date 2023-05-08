<script>
import SingleCard from './SingleCard.vue';
import { store } from '../store';
import axios from 'axios';

export default {
  name: "CardCont",
  components: {
    SingleCard,
  },
  data() {
    return {
      store,
    }
  },
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
      .then(res => {
        store.archetypes = res.data
        console.log(store.archetypes)
      })
  },
  methods: {

  }
}
</script>

<template>
  <div class="counter">
    <select v-model="store.selectedArche" class="form-select" aria-label="Default select example">
      <option selected>all</option>
      <option v-for="(element, index) in store.archetypes">{{ element.archetype_name }}</option>
    </select>
    <button type="button" class="btn btn-primary" @click.prevent="$emit('search')">cerca</button>
    <span class="text-white h6 ms-2">Found {{ store.yuGiOhCardsData.length }} cards</span>
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

  select {
    width: 200px;
    margin-right: 10px;
  }
}
</style>
