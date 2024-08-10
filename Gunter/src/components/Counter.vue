<script setup>
import {ref} from 'vue'

const count = ref(0);
let colorNumber = true;

function increaseGunter(magicNumber) {
  if (count.value >= 20) {
    return;
  }
  count.value = count.value + magicNumber
  colorGunter()
  if (count.value >= 20){
    count.value = 20
  }
}

function decreaseGunter() {
  if (count.value === 0){
    return;
  }
  count.value = count.value - 1
  colorGunter()
}

function resetGunter() {
  count.value = 0
}

function colorGunter() {
  if (count.value >= 10){
    colorNumber = false;
  }
  else {
    colorNumber = true;
  }
}

</script>

<template>
  <h1>Mon compteur</h1>
  <p :style="colorNumber ? 'color: green' : 'color:red'">{{ count }}</p>
  <button :disabled="count >= 20" @click="increaseGunter(1)">Increase</button>
  <button @click="decreaseGunter">Decrease</button>
  <button @click="resetGunter">Reset</button>
  <button :disabled="count >= 20" @click="increaseGunter(10)">Increase +10</button>
</template>

<style>
  button{
    border-radius: 3em;
    margin: 1em;
    padding: 0.5em;
  }

  p{
    margin: 1em;
  }

</style>
