<template>
    <div class="text-center cBoxBackground ms-2">
        <img class="img-fluid mt-4" :src="datiBox.poster">
        <h3>{{ datiBox.title }}</h3>
        <p>{{ datiBox.author }}</p>
        <p>{{ datiBox.year }}</p>
    </div>
</template>

<script>

export default {
    name: 'BoxAlbum',
    props: {
        datiBox: Object
    }
    

}
</script>

<style lang="scss" scoped>
@import "../../assets/style/vars.scss";

.cBoxBackground{
    width: 19%;
    background-color: $colorePrimario;
    
    h3{
        color: $coloreSecondario;
    }
    p{
        color: $coloreTerziario;
    }
}

</style>