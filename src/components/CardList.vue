<script>
    import SingleCard from './SingleCard.vue';
    import {store} from '../store.js';

    export default {
        name: 'CardList',
        components: {
            SingleCard
        },
        data(){
            return{
                store
            }
        }

    }

</script>


<template>
    <div class="container">
        <div class="row gy-3">
            <div class="col-3" v-for="(carta, index) in store.cardList" :key="index">
                <SingleCard 
                    :archetipo="carta.archetype"
                    :nome="carta.name"
                    :image="carta.card_images[0].image_url_small"
                />
            </div>
        </div>
    </div>
</template>


<style scoped lang="scss">
@use 'bootstrap';
@use '../styles/variables' as *;


</style>