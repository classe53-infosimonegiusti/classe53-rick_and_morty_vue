<template>
  <h1 class="text-center my-5">{{messaggio}}</h1>
</template>

<script>
    export default {
        name: "MyHeader",
        props: {
            "messaggio": String
        }
    }
</script>

<style lang="scss" scoped>

</style>