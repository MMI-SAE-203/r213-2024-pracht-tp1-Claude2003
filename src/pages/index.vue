<!-- eslint-disable vue/multi-word-component-names -->
<script setup lang="ts">

import { ref } from "vue";


 
const maVar = ref(true) 
</script>

<template>
  <button @click="maVar = 
  false"> cache  </button>

  <button @click="maVar =
  true"> pas cache 
  </button>

  <h1 v-show="maVar" 
  class="text-2xl">Bonjour monde !</h1>

  <button @click="maVar = 
  !maVar"> cache ou pas cache  </button>

  
  
  <h1 v-show="maVar" 
  class="text-2xl">Bonjour monde !</h1>



<p> mavar : {{maVar}} </p>
</template>