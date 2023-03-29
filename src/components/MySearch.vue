<script>
    export default {
        name: 'MySearch'
    }

</script>


<template>
    <div class="container">
        <div class="row">
            <div class="col-auto my-3">
                <input type="search" name="search" id="search" placeholder="Search">
            </div>
        </div>
    </div>
</template>


<style scoped lang="scss">
    @use '../styles/general.scss';

    .container {
        max-width: 1000px;
        margin: auto;
    }
    #search {
        width: 100px;
    }
</style>