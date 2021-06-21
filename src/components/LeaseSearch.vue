<template>
  <div>
    <select @change="changeTypeCode" v-model="announcementTypeCode">
      <option value="">전체</option>
      <option value="01">토지</option>
      <option value="05">분양주택</option>
      <option value="06">임대주택</option>
      <option value="13">주거복지</option>
      <option value="22">상가</option>
      <option value="39">신혼희망타운</option>
    </select>
    <select @change="changeRegionCode" v-model="regionCode">
      <option value="">전체</option>
      <option value="11">서울특별시</option>
      <option value="26">부산광역시</option>
      <option value="27">대구광역시</option>
      <option value="28">인천광역시</option>
      <option value="29">광주광역시</option>
      <option value="30">대전광역시</option>
      <option value="31">울산광역시</option>
      <option value="36110">세종특별자치시</option>
      <option value="41">경기도</option>
      <option value="42">강원도</option>
      <option value="43">충청북도</option>
      <option value="44">충청남도</option>
      <option value="45">전라북도</option>
      <option value="46">전라남도</option>
      <option value="47">경상북도</option>
      <option value="48">경상남도</option>
      <option value="50">제주특별자치도</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "LeaseSearch",
  data: function () {
    return {
      regionCode: '',
      announcementTypeCode: ''
    }
  },
  methods: {
    changeRegionCode: function () {
      this.$emit('changeRegionCode', this.regionCode);
    },
    changeTypeCode: function () {
      this.$emit('changeTypeCode', this.announcementTypeCode);
    }
  }
}
</script>

<style scoped>

</style>
