<script>
    export default {
        name: 'SingleCard',
        props: {
            archetipo: 'String',
            nome: 'String',
            image: 'String'
        }
    }

</script>


<template>
    <div class="container">
        <div class="row">
            <div class="col text-center">
                <img :src="image" :alt="nome">
                <h6>{{archetipo}}</h6>
                <h6>{{nome}}</h6>
            </div>
        </div>
    </div>

</template>


<style scoped lang="scss">
@use 'bootstrap';

@use '../styles/variables' as *;
    .col {
        background-color: $My-color-primary;
 
    }
    img{
        min-height: 300px;
    }

</style>