<script setup>
  const props = defineProps(['msg', 'num'])
</script>

<template>
  <header class="header">
    <p>Header</p>
    <span>{{ msg }}</span>
    <div>{{ num }}</div>
  </header>
</template>

<style scoped>
p {
  font-weight: 500;
  font-size: 2.6rem;
}
</style>
