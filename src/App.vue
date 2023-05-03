<script setup>
import SelectDinner from './components/SelectDinner.vue'
</script>

<template>
  <section id="app">
    <header>
      <h1>🍄晚餐選擇器🍄</h1>  
    </header>

    <main>
      <SelectDinner />
    </main>
  </section>
</template>

<style scoped>
#app {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
header {
  line-height: 1.5;
  text-align: center;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    text-align: center;
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
