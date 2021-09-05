<template>
  <h1>{{ preferredName }}</h1>
</template>

<script>
export default {
  name: 'Title',
  props: {
    preferredName: String
  }
}
</script>

<style scoped>
h1 {
  color: peru;
}
</style>