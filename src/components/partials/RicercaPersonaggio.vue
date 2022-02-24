<template>
  <div>
      <form class="d-flex"> 
            <input  class="form-control flex-grow-1"  type="text" v-model="ricerca">
            <!--<button @click="$emit('ricerca', ricerca)">Ricerca</button>-->
            <button type="submit" class="btn btn-primary" @click.prevent="faiRicerca">Ricerca</button>
      </form>
  </div>
</template>

<script>
    export default {
        name: "RicercaPersonaggio",
        data() {
            return {
                ricerca: "",
            }
        },
        methods: {
            faiRicerca() {
                console.log('Il componente figlio ha inviato: ' + this.ricerca);
                this.$emit('eventoRicerca', this.ricerca);
            }
        }
    }
</script>

<style>

</style>