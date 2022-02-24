<template>
    <div class="container">

        <RicercaPersonaggio @eventoRicerca='effettuaRicerca' />

        <div class="row row-cols-4">
        
            <CardPersonaggio 
                v-for="personaggio in listaPersonaggiFiltrati" 
                :key="personaggio.id"
                :personaggio="personaggio" 
            />
            
        </div>

        <ConteggioPersonaggi :conteggio="listaPersonaggiFiltrati.length" />

        <LoadInProgress v-if="loadingInProgress" />

    </div>

</template>

<script>

    //integro axios nel mio progetto partendo dalla copia presente in node_modules
    const axios = require('axios');

    import CardPersonaggio from './partials/CardPersonaggio.vue';
    import ConteggioPersonaggi from './partials/ConteggioPersonaggi.vue';
    import RicercaPersonaggio from './partials/RicercaPersonaggio.vue';
    import LoadInProgress from './LoadInProgress.vue';

    export default {
        name: "ListaPersonaggi",
        data() {
            return {
                listaPersonaggi: [],
                loadingInProgress: true,
                endpoint: 'https://api.sampleapis.com/rickandmorty/characters',
                testoRicercato: ''
            }
        },
        components: {
            CardPersonaggio,
            ConteggioPersonaggi,
            RicercaPersonaggio,
            LoadInProgress
        },

        computed: {
            listaPersonaggiFiltrati() {
                if (this.testoRicercato == "") {
                    return this.listaPersonaggi;
                } else {
                    return this.listaPersonaggi.filter(item => {
                        return item.name.toLowerCase().replaceAll(' ', '').includes(this.testoRicercato.toLowerCase().replaceAll(' ', ''));
                    });
                }
            }
        },

        methods: {

            effettuaRicerca(testo) {
                this.testoRicercato = testo;
            },

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