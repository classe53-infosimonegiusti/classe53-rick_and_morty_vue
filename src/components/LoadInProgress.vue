<template>
  <div class="loader">
    <h1>
        Caricamento in corso...
    </h1>
  </div>
</template>

<script>
export default {
    name: 'LoadInProgress',
}
</script>

<style scoped lang="scss">

    .loader {
        position: fixed;
        left: 0;
        top: 0;
        width: 100vw;
        height: 100vh;
        background-color: #fff;
        display: flex;
        justify-content: center;
        align-items: center;

        h1 {
            font-size: 40px;
        }
    }


</style>