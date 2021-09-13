<template>
  <div class="weather-wrap">
    <div class="location-box">
      <div class="location">Lille, FRANCE</div>
      <div class="date">Monday 13 September 2021</div>
    </div>
    <div class="weather-box">
      <div class="temperature">21°</div>
      <div class="weather">Cloudy</div>
    </div>
  </div>
</template>

<style scoped>
.location-box {
    color: white;
    font-size: 32px;
    text-align: center;
    text-shadow: 1px 1px rgba(0, 0, 0, 0.25);
    margin-bottom: 0.5rem;
    font-weight: 700;
}

.date {
    font-size: 20px;
    font-weight: 300;
    font-style: italic;
}

.weather-box {
    text-align: center;
    color: white;
    text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}

.temperature {
    display: inline-block;
    padding: 1rem 2rem;
    font-size: 102px;
    font-weight: 900;
    background-color: rgba(255, 255, 255, 0.25);
    border-radius: 1rem;
    margin: 3rem 0rem;
    box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}

.weather {
    font-size: 48px;
    font-weight: 700;
    font-style: italic;
}
</style>
