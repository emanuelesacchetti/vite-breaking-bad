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
                <h5>{{nome}}</h5>
            </div>
        </div>
    </div>

</template>


<style scoped lang="scss">
@use 'bootstrap';

@use '../styles/variables' as *;
    
.col {
    height: 400px;
    background-color: $My-color-primary;
}
    img{
        height: 70%;
        padding: 5px;
    }
    h6 {
        color: white;
        padding: 10px;
    }

</style>