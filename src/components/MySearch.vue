<script>
    export default {
        name: 'MySearch',
        props:{
            race: Array
        },
        data(){
            return{
                
            }
        }
    }

</script>


<template>
    <div class="container">
        <div class="row">
            <div class="col-auto my-3">
                <select>
                    <option v-for="singleRace in this.race" >
                        {{ singleRace }}
                    </option>
                    
                </select>
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