<template>
  <section class="container">

        <Select 
        @selectDato="filtroGenere"/>

        <div v-if="selectEmit!=''" class="container">
            <div class="row row-cols-1 row-cols-sm-2 row-cols-md-5 row-cols-lg-5 mt-5">
                <BoxAlbum
                    v-for="(BxAlbum, index) in arrayFiltrato" 
                    :key="index"
                    :datiBox="BxAlbum"
                    class="col mt-2" />
            </div>
        </div>
        <div v-else class="container">
            <div class="row row-cols-1 row-cols-sm-2 row-cols-md-5 row-cols-lg-5 mt-5">
                <BoxAlbum
                    v-for="(BxAlbum, index) in datiBoxArr" 
                    :key="index"
                    :datiBox="BxAlbum"
                    class="col mt-2" />
            </div>
        </div>
        

  </section>
</template>

<script>
import BoxAlbum from '../section/BoxAlbum.vue'
import Select from './Select.vue'
import axios from 'axios'


export default {
name: 'Album',
    components: {
        BoxAlbum,
        Select
    },
    data() {
        return{
            getAPI: "https://flynn.boolean.careers/exercises/api/array/music",
            datiBoxArr: [],
            selectEmit: ""
        }
        
    },
    created() {
        this.getAlbum();
    },
    computed: {
        arrayFiltrato() {
            return this.datiBoxArr.filter( disco => disco.genre.toLowerCase() == this.selectEmit.toLowerCase() )
        }
    },
    methods: {
        getAlbum(){
            axios.get(this.getAPI)
            .then( (datiAlbum) => {
                // handle success
                this.datiBoxArr = datiAlbum.data.response;

            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
            .then(function () {
                // always executed
            });
        },
        filtroGenere: function(genereSelezionato) {
             this.selectEmit = genereSelezionato;
             console.log(this.selectEmit);
        }
    }

}
</script>

<style lang="scss" scoped>


</style>