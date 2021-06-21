<template>
  <div>
    <button @click="nextPage">다음페이지</button>
  </div>
</template>

<script>
export default {
  name: "LeaseFooter",
  methods: {
    nextPage: function () {
      this.$emit('nextPage');
    }
  }
}
</script>

<style scoped>

</style>
