<template>
  <div class="semaforo">
    
    <div class="columna">
      <button @click="changeLight('red')" class="color-button red-button">Red</button>
      <button @click="changeLight('yellow')" class="color-button yellow-button">Yellow</button>
      <button @click="changeLight('green')" class="color-button green-button">Green</button>
    </div>

    
    <div class="colum">
      <Light color="red" :isActive="currentLight === 'red'" />
      <Light color="yellow" :isActive="currentLight === 'yellow'" />
      <Light color="green" :isActive="currentLight === 'green'" />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Light from '~/components/Light.vue';

const currentLight = ref('red'); 

function changeLight(color) {
  currentLight.value = color;
}
</script>

<style scoped>

.semaforo {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 20px;
  padding-top: 20px;
}


.button-column {
  display: flex;
  flex-direction: column;
  gap: 20px;
}


.semaforo {
  width: 100px;
  background-color: #383838;
  padding: 20px;
  border-radius: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.color-button {
  padding: 5px 10px;
  border: none;
  border-radius: 10px;
  color: white;
  font-weight: bold;
  cursor: pointer;
  width: 80px;
  text-align: right;
}


.red-button {
  background-color: red;
}
.yellow-button {
  background-color: yellow;
  color: black;
}
.green-button {
  background-color: green;
}
</style>

