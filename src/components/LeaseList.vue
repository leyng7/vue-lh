<template>
  <div id="card-container">
    <div class="card" v-for="notice in notices" v-bind:key="notice.PAN_ID">
      <div>{{ notice.PAN_SS }} ({{ notice.PAN_NT_ST_DT }} ~ {{ notice.CLSG_DT }})</div>
      <div>{{ notice.PAN_NM }}</div>
      <div>{{ notice.UPP_AIS_TP_NM }} {{ notice.AIS_TP_CD_NM }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "LeaseList",
  props: {
    notices: Array
  },
}
</script>

<style scoped>
#card-container {
  /*display: flex;
  justify-content: center;*/
}
.card {
  width: 500px;
  min-height: 50px;
  padding: 5px;
  border-radius: 0 5px;
  margin: 0 auto 10px;
  box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03);
  background-color: white;
}
</style>
