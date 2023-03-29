<script>
  import MyHeader from './components/MyHeader.vue';
  import MySearch from './components/MySearch.vue';
  import CentralBox from './components/CentralBox.vue';

  export default {
    components: {
      MyHeader,
      CentralBox,
      MySearch
    }
  }
</script>


<template>
  <MyHeader />

  <main>
    <MySearch />
    <CentralBox />
  </main>
 
</template>


<style scoped lang="scss">
  @use './styles/general.scss';
  @use './styles/variables' as*;

  main {
    background-color: $My-color-primary;
    height: calc(100vh - 70px);
  }

</style>
