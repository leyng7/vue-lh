<template>
  <div id="card-container" v-if="!isLoading">
    <div class="card" v-for="notice in notices" v-bind:key="notice.PAN_ID">
      <div class="card-body">
        <div class="dt">[{{ notice.UPP_AIS_TP_NM }}] {{ notice.PAN_NT_ST_DT }} ~ {{ notice.CLSG_DT }}</div>
        <div class="pan-nm">
          <a v-bind:href="notice.DTL_URL" target="_blank">
            {{ notice.PAN_NM }}
          </a>
        </div>
<!--        {{ notice.AIS_TP_CD_NM }}-->
      </div>
      <div>
        <div class="pan-ss">{{ notice.PAN_SS }}</div>
      </div>
    </div>
  </div>
  <div id="loading" v-else>
    <div>데이터 불러오는중...</div>
  </div>
</template>

<script>
export default {
  name: "LeaseList",
  props: {
    notices: Array,
    isLoading: Boolean
  },
}
</script>

<style scoped>
#loading {
  min-height: 500px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.card {
  width: 500px;
  min-height: 50px;
  padding: 5px;
  border-radius: 0 5px;
  margin: 0 auto 10px;
  box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03);
  display: flex;
  justify-content: space-between;
}

.dt {
  font-size: 12px;
}

.pan-nm {
  font-size: 14px;
  width: 400px;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.type {
  font-size: 12px;
}

.pan-ss {
  text-align: center;
  min-width: 50px;
  font-size: 12px;
  padding: 5px;
  color: white;
  background-color: #D1B6E1;
  border-radius: 5px;
}
</style>
