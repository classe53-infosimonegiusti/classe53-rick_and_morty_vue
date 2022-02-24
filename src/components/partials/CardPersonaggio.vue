<template>
    <div class="p-3 text-center">
        <img class="rounded-circle " :src="personaggio.image">
        <h2>{{personaggio.name}}</h2>
        <div>{{personaggio.origin}}</div>
        <div>{{personaggio.gender}}</div>
    </div>
</template>

<script>
export default {
    name: 'CardPersonaggio',
    props: {
        "personaggio": Object
    }
}
</script>

<style>

</style>
