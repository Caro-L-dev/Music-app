<script>
import SearchBoxWeather from "./SearchBoxWeather.vue";
import WrapWeather from "./WrapWeather.vue";
export default {
  components: {
    SearchBoxWeather,
    WrapWeather,
  },
  data() {
    return {
      api_key: (process.env.OPEN_WEATHER_API_KEY),
    };
  },
};
</script>

<template>
  <div class="bg-weather">
    <main>
      <search-box-weather />
      <wrap-weather />
    </main>
  </div>
</template>


<style>
.bg-weather {
    font-family: Arial, Helvetica, sans-serif;
    background-image: url('../../assets/mountain01.jpg');
    background-size: cover;
    padding: 2rem;
    border-radius: 1rem;
}
</style>
