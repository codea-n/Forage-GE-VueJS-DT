<script setup>
import { ref, computed } from "vue";
const msg = ref("Hello World!");
const num1 = ref(15);
const num2 = ref(20);
const sum = computed(() => num1.value + num2.value);
const buttonClicked = ref(false);
const handleClick = () => {
  buttonClicked.value = true;
};
</script>

<template>
  <h1>{{ msg }}</h1>
  <h2>Task 2: Compute Product</h2>
  <input v-model="msg" />
  <br />
  <p>Task 3: Below is an image of the space taken from Wikipedia</p>
  <img src="./assets/space_image.jfif" alt="Space Image" />

  <!-- Displaying the values of the variables -->
  <h2>Task4: Show numbers that were added</h2>
  <p>{{ num1 }} +{{ num2 }} = {{ sum }}</p>

  <h2>Task5: Add button to calculate sum</h2>
  <button v-if="!buttonClicked" @click="handleClick">Calculate Sum</button>
  <p v-if="buttonClicked">The sum is {{ sum }}</p>
</template>
