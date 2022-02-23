<template>
    <div class="container">
        <div class="row">
            <CardPersonaggio 
                v-for="personaggio in listaPersonaggi" 
                :key="personaggio.id" 
                :pippo="personaggio" 
            />
        </div>

        <ConteggioPersonaggi :conteggio="listaPersonaggi.length" />

    </div>

</template>

<script>

    //integro axios nel mio progetto partendo dalla copia presente in node_modules
    const axios = require('axios');

    import CardPersonaggio from './partials/CardPersonaggio.vue';
    import ConteggioPersonaggi from './partials/ConteggioPersonaggi.vue';

    export default {
        name: "ListaPersonaggi",
        data() {
            return {
                listaPersonaggi: [],
                loadingInProgress: true,
                endpoint: 'https://api.sampleapis.com/rickandmorty/characters'
            }
        },
        components: {
            CardPersonaggio,
            ConteggioPersonaggi
        },
        methods: {
            getPersonaggi() {
                // Make a request for a user with a given ID
                axios.get(this.endpoint)
                .then((response) => {
                    this.listaPersonaggi = response.data;
                    this.loadingInProgress = false;
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
            }
        },
        mounted() {
            
        },
        created() {
            this.getPersonaggi();
        }

    }
</script>

<style>

</style>