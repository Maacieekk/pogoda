<template>
  <div v-if="Object.keys(values).length == 0" class="loading">loading...</div>
  <div v-else class="CityDetails">
    <h2>{{ values.name }}</h2>
    <img class="flag"
      :src="'https://countryflagsapi.com/svg/' + values.country"
      alt="COUNTRY FLAG"
    />
    <div class="suntime">
      <div class="sunrise">{{ unixToDateTime(values.sunrise) }}</div>
      <div class="sunset">{{ unixToDateTime(values.sunset) }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    values: Object,
  },
  methods: {
    unixToDateTime(unix_timestamp) {
      const date = new Date(unix_timestamp * 1000);
      const hours = date.getHours();
      const minutes = '0' + date.getMinutes();
      const seconds = '0' + date.getSeconds();
      return hours + ':' + minutes.substr(-2) + ':' + seconds.substr(-2);
    },
  },
};
</script>

<style lang="scss">
.flag {
  max-width: 30vw;
  -webkit-box-shadow: 16px 8px 24px 0px rgba(66, 68, 90, 1);
-moz-box-shadow: 16px 8px 24px 0px rgba(66, 68, 90, 1);
box-shadow: 16px 8px 24px 0px rgba(66, 68, 90, 1);
}
.CityDetails
 {
   -webkit-box-shadow: 16px 8px 24px 0px rgba(66, 68, 90, 1);
-moz-box-shadow: 16px 8px 24px 0px rgba(66, 68, 90, 1);
box-shadow: 16px 8px 24px 0px rgba(66, 68, 90, 1);
  
  justify-content: center;
  align-items: center;
  header {
    display: flex;
    h2 {
      margin: 0;
    }
  }
}
</style>
