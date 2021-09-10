<script>
export default {
  props: ["title"],
};
</script>

<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
</template>

<style scoped>
header {
  display: flex;
  justify-content: center;
  font-family: sans-serif;
}

h1 {
  font-size: 24px;
  color: #131a26;
  font-weight: 700;
  text-align: center;
  text-transform: uppercase;
  padding-bottom: 0.3rem;
  border-bottom: 0.2rem solid #0984e3;
}
</style>