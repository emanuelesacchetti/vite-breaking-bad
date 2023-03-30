<script>
    import {store} from '../store.js'

    export default {
        name: 'MySearch',
        props:{
            race: Array
        },
        data(){
            return{
                store,
                
            }
        }/*,
        methods: {
            pippo(){
                console.log(this.raceName);
                console.log(this.store.raceSelected);
                if(!this.store.raceSelected.includes(this.raceName)){
                    this.store.raceSelected += this.raceName
                }
            }
        }*/
    }

</script>


<template>
    <div class="container">
        <div class="row">
            <div class="col-auto my-3">
                <select name="race" v-model="this.store.raceSelected">
                    <option v-for="singleRace in this.race" @change="$emit('ricerca')">
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