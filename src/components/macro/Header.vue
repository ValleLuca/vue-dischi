<template>
    <div class="setContLogo">
      <img class="img-fluid imgSet" src="https://www.telechargerici.fr/wp-content/uploads/2019/06/spotify-logo.png">
    </div>
</template>

<script>


export default {
name: 'Header',
  components: {
  },
  
}
</script>

<style lang="scss" scoped>
@import "../../assets/style/vars.scss";

.setContLogo{
  background-color: $colorePrimario;
  display: flex;
  align-items: center;
}

.imgSet{
  height: 70px;
  padding: 10px;
}

</style>