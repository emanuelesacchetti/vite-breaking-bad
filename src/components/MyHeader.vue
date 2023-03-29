<script>
    export default {
        name: 'MyHeader'
    }

</script>


<template>
    <header class="d-flex align-items-center">
        <img src="../../public/logo.jpg" alt="logo Yu-Gi-Oh">
        <h1>Yu-Gi-Oh API</h1>       
    </header>
</template>


<style scoped lang="scss">
@use 'bootstrap';
    header {
        height: 70px;
    }
    img {
        height: 50%;
    }
</style>