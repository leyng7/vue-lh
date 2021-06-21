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
button {
  background-color: white; /* Green */
  border: none;
  color: black;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03);
  cursor: pointer;
}
</style>
