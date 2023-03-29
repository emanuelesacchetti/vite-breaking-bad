<script>
  import MyHeader from './components/MyHeader.vue';
  import MySearch from './components/MySearch.vue';
  import CentralBox from './components/CentralBox.vue';
  import axios from 'axios';
  import {store} from './store.js';

  export default {
    components: {
      MyHeader,
      CentralBox,
      MySearch
    },
    data(){
      return{
        store
      }
    },
    created(){
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=Blue-Eyes')
        .then(response => {
          this.store.cardList = response.data.data
          console.log(this.store.cardList)
        })
    }
  }
</script>


<template>
  <MyHeader />

  <main>
    <MySearch />
    <CentralBox />
  </main>
 {{  }}
</template>


<style scoped lang="scss">
  @use './styles/general.scss';
  @use './styles/variables' as*;

  main {
    background-color: $My-color-primary;
    height: 100%;
  }

</style>
