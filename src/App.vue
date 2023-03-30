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
        store,
        searchResult: []
      }
    },
    methods: {
      
      getRace(){
        console.log('getRace')
        this.store.cardList.forEach((element) => {

          console.log(element.race);
          this.searchResult.push(element.race);
          console.log(this.searchResult);
        } );
        
      },

      getAliens(){
        console.log('getAlien')
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=Alien')
        .then(response => {
          console.log(response);
          this.store.cardList = response.data.data;
          console.log(this.store.cardList);
          this.getRace()
        })
      }
    },
    created(){
      this.getAliens()
    }
  }
</script>


<template>
  <MyHeader />

  <main>
    <MySearch :race="this.searchResult"/>
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
