<template>
  <div class="single">
  <h3>{{values.dt_txt}}</h3>
 <div class="temp">
<ul>
<li>temp: {{values.main.temp}} </li>
<li>temp min: {{values.main.temp_min}} </li>
<li>temp max: {{values.main.temp_max}} </li>
<li>ciśnienie: {{values.main.pressure}} </li>
</ul>
<img :src="'http://openweathermap.org/img/wn/'+values.weather[0].icon+'.png'" alt="zdjecie">
 </div>
  </div>
 
</template>
<script>
export default {
  props: {
    values: Object,
  },
};
</script>

<style lang="scss">
.single {
  
  margin:1rem;
  border-radius:1rem;
  
h3{margin:0;
border-radius:1rem 1rem 0 0;
color:#ffffff;
background-color:#213547;
padding: .5rem;
}
.temp{
display:flex;
justify-content:space-between;
aspect-ratio:1/1;
padding:.5rem 0 0 1rem;
ul{
  padding:0;margin:0;list-style:none;
  li{ text-align:left;}
  }
  img{
    width:50%;
    height: 50%;
    aspect-ratio:1/1;
  }
}
}

</style>
