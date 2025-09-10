<template>
  <div class="container">
    <!-- Heading -->
    <h1>Compute Product</h1>

    <!-- Image -->
    <img 
      src="https://vuejs.org/images/logo.png" 
      alt="Vue Logo" 
      class="logo"
    />

    <!-- Display numbers -->
    <p>Number 1: {{ num1 }}</p>
    <p>Number 2: {{ num2 }}</p>

    <!-- Button or Result -->
    <div v-if="!computed">
      <button @click="computeProduct">Compute</button>
    </div>
    <div v-else>
      <p>The product is: {{ product }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// Variables for numbers
const num1 = ref(7)
const num2 = ref(5)

// State for computation
const product = ref(null)
const computed = ref(false)

// Function to compute product
function computeProduct() {
  product.value = num1.value * num2.value
  computed.value = true
}
</script>

<style>
.container {
  text-align: center;
  margin-top: 30px;
  font-family: Arial, sans-serif;
}

.logo {
  width: 120px;
  margin: 20px 0;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  background-color: #42b883;
  color: white;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #2c9d6f;
}
</style>
