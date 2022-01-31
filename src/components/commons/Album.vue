<template>
  <section class="container">
    <div class="row row-cols-1 row-cols-sm-2 row-cols-md-5 row-cols-lg-5 mt-5">
        <BoxAlbum
            v-for="(BxAlbum, index) in datiBoxArr" 
            :key="index"
            :datiBox="BxAlbum"
            class="col mt-2" />
    </div>
  </section>
</template>

<script>
import BoxAlbum from '../section/BoxAlbum.vue'
import axios from 'axios'


export default {
name: 'Album',
    components: {
        BoxAlbum
    },
    data() {
        return{
            getAPI: "https://flynn.boolean.careers/exercises/api/array/music",
            datiBoxArr: [] 
        }
        
    },
    created() {
        this.getAlbum();
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
        }
    }

}
</script>

<style lang="scss" scoped>


</style>