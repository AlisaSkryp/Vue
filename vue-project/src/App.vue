<script setup>
import { reactive } from 'vue'
import Header from "./components/Header.vue";

const state = reactive({ num: 0 })

function increment() {
  state.num++
}
</script>

<template>
  <header>
    <div class="wrapper">
      <Header msg="You did it!" :num="state.num" />
      <button @click="increment">
        INCREMENT
      </button>
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
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
