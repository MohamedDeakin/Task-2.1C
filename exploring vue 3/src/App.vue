<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />

    <!-- Conditional Rendering Examples -->
    <div>
      <h2>Conditional Rendering</h2>

      <!-- v-if: Display a message if awesome is true -->
      <h1 v-if="awesome">Vue is awesome!</h1>

      <!-- v-else: Toggle awesome value with a button -->
      <button @click="awesome = !awesome">Toggle</button>
      <h1 v-if="awesome">Dev!</h1>
      <h1 v-else>Oh no 🤣</h1>

      <!-- v-show: Toggle visibility based on showGreeting -->
      <h2>Greeting:</h2>
      <h1 v-show="showGreeting">Hello! 🏄‍♂️</h1>
      <button @click="showGreeting = !showGreeting">Toggle</button>

      <!-- v-for example: Loop through a list of fruits -->
      <h2>Fruits:</h2>
      <ul>
        <li v-for="(fruit, index) in fruits" :key="index">{{ fruit }}</li>
      </ul>
    </div>

    <!-- Form Input Handling Example -->
    <div>
      <h2>Form Input Handling</h2>

      <!-- Select element with v-model for multiple options -->
      <div>Selected: {{ selected }}</div>
      <select v-model="selected" multiple>
        <option value="A">A</option>
        <option value="B">B</option>
        <option value="C">C</option>
      </select>
    </div>
  </main>
</template>

<script setup>
import { ref } from 'vue'; // Import ref from Vue

import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'

// Define isTrue, isVisible, and selected as refs
const isTrue = ref(true);
const isVisible = ref(true);
const selected = ref(['A']); // Initialize selected with a default value (an array)

// New data properties for examples
const awesome = ref(true); // For v-if example
const showGreeting = ref(true); // For v-show example
const fruits = ref(['Apple', 'Banana', 'Cherry', 'Date', 'Fig']); // For v-for example
</script>

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
