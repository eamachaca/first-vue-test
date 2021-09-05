<template>
  <button @click="changeBalance" :disabled="disabled">{{ text }}</button>
</template>

<script>
export default {
  name: "BalanceAction",
  props: {
    text: String,
    disabled: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    changeBalance() {
      this.$emit('action')
    }
  }
}
</script>

<style scoped>

</style>