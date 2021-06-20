<template>
  <div id="card-container">
    <div class="card" v-for="notice in notices" v-bind:key="notice.PAN_ID">
      <div>{{ notice.PAN_SS }} ({{ notice.PAN_NT_ST_DT }} ~ {{ notice.CLSG_DT }})</div>
      <div>{{ notice.PAN_NM }}</div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "LeaseList",
  data: function () {
    return {
      notices: []
    }
  },
  methods: {
    getData: () => {

    }
  },
  created: function () {
    const vm = this;
    axios
        .get('/api/lhLeaseNoticeInfo')
        .then(response => {
          console.log(response.data[0]);
          vm.notices = response.data;
        })
        .catch(error => {
          console.log(error);
        })
  }
}
</script>

<style scoped>
#card-container {
  /*display: flex;
  justify-content: center;*/
}
.card {
  width: 500px;
  height: 50px;
  padding: 5px;
  border-radius: 0 5px;
  margin: 0 auto 10px;
  box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03);
  background-color: white;
}
</style>
