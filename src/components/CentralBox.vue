<script>
import CardList from './CardList.vue';
import FoundCount from './FoundCount.vue';

    export default {
        name: 'CentralBox',
        components: {
            CardList,
            FoundCount
        }
    }

</script>


<template>
    <div class="box container">
        <div class="row d-flex flex-column">
                <FoundCount class="col-11"/>
                <CardList class="col-11"/>
        </div>
    </div>
    
</template>


<style scoped lang="scss">
@use 'bootstrap';
    .box {
        background-color: white;
        max-width: 1000px;
        margin: auto;
        min-height: 500px;
        padding: 30px;
    }
 
</style>