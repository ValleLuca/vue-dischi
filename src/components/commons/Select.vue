<template>
    <div>
        <select name="genere" @change="salvaGenere">
            <option value="">Scegli il genere</option>
            <option value="pop">Pop</option>
            <option value="rock">Rock</option>
            <option value="jazz">jazz</option>
            <option value="metal">Metal</option>
        </select>
    </div>
</template>

<script>

export default {
    name: 'select',
    data() {
        return {
            genereSelezionato: ""
        }
    },
    methods: {
        salvaGenere:function (e) {
            this.genereSelezionato = e.target.value;
            this.$emit('selectDato', this.genereSelezionato);
        }
    }
}
</script>

<style lang="scss" scoped>



</style>