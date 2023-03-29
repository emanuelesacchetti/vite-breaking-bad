<script>
    import SingleCard from './SingleCard.vue';

    export default {
        name: 'CardList',
        components: {
            SingleCard
        }

    }

</script>


<template>
    <div class="container">
        <div class="row">
            <SingleCard class="col-3"/>
        </div>
    </div>
</template>


<style scoped lang="scss">
@use 'bootstrap';
    .col-3 {
        height: 100px;
        background-color: red;
    }
</style>