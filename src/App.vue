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
        searchResult: [],
        urlArchetypes: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=Alien'
      }
    },
    methods: {
      
      getRace(){
        this.store.cardList.forEach((element) => {
          this.searchResult.push(element.race);
        } );
        
      },

      getAliens(){
        axios.get(this.urlArchetypes)
        .then(response => {
          this.store.cardList = response.data.data;
          this.getRace()
        })
      },
      getSelectedRace(){
        let razzaSingolaList= []
        this.store.raceSelected.forEach((element)=>{
          if(!razzaSingolaList.includes(element)){
            razzaSingolaList.push(element)
          }
          console.log(razzaSingolaList)
        })
        
        razzaSingolaList.forEach((singolaRazza)=>{
          if(singolaRazza == this.store.raceSelected){
            this.urlArchetypes += `&race=${this.store.raceSelected}`;
            axios.get(this.urlArchetype)
            .then(response => {
              this.store.cardList = response.data.data;
        })
          }
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
    <MySearch :race="this.searchResult" @ricerca="getSelectedRace"/>
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
