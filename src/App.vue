<template>
  <div id="app">
    <LeaseSearch
        v-on:changeRegionCode="changeRegionCode"
        v-on:changeTypeCode="changeTypeCode"
    />
    <LeaseList v-bind:notices="notices"/>
    <LeaseFooter v-on:nextPage="nextPage"/>
  </div>
</template>

<script>
import LeaseList from "./components/LeaseList";
import axios from "axios";
import LeaseSearch from "./components/LeaseSearch";
import LeaseFooter from "./components/LeaseFooter";

export default {
  name: 'App',
  components: {
    LeaseFooter,
    LeaseSearch,
    LeaseList,
  },
  data: function () {
    return {
      notices: [],
      regionCode: '',
      announcementTypeCode: '',
      page: 1
    }
  },
  methods: {
    changeRegionCode: async function (regionCode) {
      this.page = 1;
      this.regionCode = regionCode;
      this.notices = await this.getNotices();
    },
    changeTypeCode: async function (typeCode) {
      this.page = 1;
      this.announcementTypeCode = typeCode;
      this.notices = await this.getNotices();
    },
    nextPage: async function () {
      this.page += 1;
      const data = await this.getNotices();
      this.notices.push(...data);
    },
    getNotices: async function () {

      const {data} = await axios
          .get('/api/lhLeaseNoticeInfo', {
            params: {
              page: this.page,
              regionCode: this.regionCode,
              announcementTypeCode: this.announcementTypeCode
            }
          });

      return data;
    }
  },
  created: function () {
    const vm = this;
    axios
        .get('/api/lhLeaseNoticeInfo')
        .then(response => {
          vm.notices = response.data;
        })
        .catch(error => {
          console.log(error);
        });
  }
}
</script>

<style>
body {
  background-color: #42b983;
}
</style>
