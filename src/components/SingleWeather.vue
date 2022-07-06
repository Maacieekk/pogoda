<template>
  <div class="single">
    

 <h3>{{values.dt_txt}} </h3>
 <div class="temp">
<ul>
<li>temp: {{values.main.temp}} </li>
<li>temp min: {{values.main.temp_min}} </li>
<li>temp max: {{values.main.temp_max}} </li>
<li>ciśnienie: {{values.main.pressure}} </li>
</ul>
<img :src="'http://openweathermap.org/img/wn/'+values.weather[0].icon+'@2x.png'" alt="zdjecie">
 </div>
  </div>
  {{values}}
</template>
<script>
export default {
  props: {
    values: Object,
  },
};
</script>

<style>
.single {
  border: 2px dashed red;
}
</style>
