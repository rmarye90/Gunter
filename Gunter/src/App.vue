<script setup>
  import { ref } from 'vue';
  import Counter from './components/Counter.vue'
  const toggleGunter = ref(true)

  function showGunter() {
    toggleGunter.value = !toggleGunter.value;
  }

</script>

<template>
  <button @click="showGunter">show BB</button>
  <section v-if="toggleGunter">
    <Counter />
  </section>
  
</template>

<style scoped>
  button{
    position: absolute;
    right: 0;
  }
</style>