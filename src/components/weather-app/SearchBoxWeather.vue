<template>
  <div class="search-box">
    <input type="text" class="search-bar" placeholder="Search..." />
  </div>
</template>

<style scoped>
.search-box,
.search-bar {
  width: 100%;
  appearance: none;
  border: none;
  outline: none;
  background: none;
  color: aliceblue;
  font-weight: 700;
  font-size: 16px;
}

.search-box {
  margin-bottom: 2rem;
}

.search-bar {
  display: block;
  padding: 1rem;
  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
  background: rgba(255, 255, 255, 0.25);
  border-radius: 0px 16px 0px 16px;
  transition: 0.4s;
}

.search-box .search-bar:focus {
  box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
  background: rgba(255, 255, 255, 0.25);
  border-radius: 16px 0px 16px 0px;
}
</style>
