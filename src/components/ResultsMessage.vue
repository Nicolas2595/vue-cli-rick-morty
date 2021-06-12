<template>
  <h2 class="text-center mt-3">TROVATI {{ number }} PERSONAGGI</h2>
</template>

<script>
export default {
    name: "ResultsMessage",
    props: ['number']
}
</script>

<style lang="scss" scoped>

  h2 {
    background-color: #9dcb38;
    border-radius: 20px;
    color: white;
  }

</style>