<template>
    <div class="col" >
        <img :src="pippo.image">
        <h2>{{pippo.name}}</h2>
        <div>{{pippo.origin}}</div>
        <div>{{pippo.gender}}</div>
    </div>
</template>

<script>
export default {
    name: 'CardPersonaggio',
    props: {
        "pippo": Object
    }
}
</script>

<style>

</style>
