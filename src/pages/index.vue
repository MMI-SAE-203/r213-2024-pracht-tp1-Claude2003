<!-- eslint-disable vue/multi-word-component-names -->
<script setup lang="ts">

import { ref } from "vue";

const sectionOpen = ref(1)
 
const maVar = ref(true) 
const toggleSection = (key) => {
  if (sectionOpen.value === key) {
    sectionOpen.value = null
  } else {
    sectionOpen.value = key
  }
}

const sectionsData = [
    {
      label: 'bouton 1',
      texte: `texte panneau 1 Lorem ipsum dolor sit ame
      consectetur adipisicing elit. Inventore animi dolore,
      rerum magni laudantium quod excepturi laboriosam, 
      ex modi debitis harum reprehenderit eaque quam ut
      ea molestiae. Id, cum dolor!`
    },
    {
      label: 'bouton 2',
      texte: `texte panneau 2 Amet alias provident quos quis, 
      Officia ut ab dolores quos dolorem accusamus ad,
      consectetur unde minima, ipsum eligendi inventore id
      labore, laborum rerum laboriosam corrupti iste.
      Distinctio, perspiciatis!`
    },
    {
      label: 'bouton 3',
      texte: `texte panneau 3 Repudiandae corporis voluptates, 
      odit reprehenderit sint pariatur at voluptatum, cumque
      quia sit eligendi ex culpa eos, alias magnam molestiae
      id modi accusantium ipsa eveniet accusamus. Tempora 
      quis corporis et nam.`
    }
  ]

</script>

<template>



<section>
  <h1 class="font-bold text-2xl mt-3">  Accordeon </h1>
    <button class="btn text-xl" @pointerdown="sectionOpen = 1">Bouton1 </button>
    <p v-show="sectionOpen === 1">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
</section>

<section>
    <button class="btn text-xl" @pointerdown="sectionOpen = 2">Bouton2 </button>
    <p v-show="sectionOpen === 2">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
</section>

<section>
    <button class="btn text-xl" @pointerdown="sectionOpen = 3">Bouton3 </button>
    <p v-show="sectionOpen === 3">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
</section>
<h1 class="font-bold text-2xl mt-3"> Section boucle </h1>
<section v-for="({ label, texte }, key) of sectionsData" :v-key="key">
    <pre class="font-mono">key : {{ key }}</pre>
    <pre class="font-mono">label : {{ label }}</pre>
    <pre class="font-mono">texte : {{ texte }}</pre>
  </section>

  <h1 class="font-bold text-2xl mt-3"> Section boucle accordeon </h1>

  <section class="mt-3" v-for="({ label, texte }, key) of sectionsData" :key="key">
      <button class="btn text-xl font-mono" @click="toggleSection(key)">{{ label }}</button>
      <p class="font-mono" v-show="sectionOpen === key">{{ texte }}</p>
    </section>


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

<!-- Désactive les vérifications ESLint spécifiques aux noms de composants multi-mots -->

<script setup lang="ts">
  // Importe la fonction 'ref' de Vue pour créer des références réactives
  import { ref } from "vue";

  // Crée une référence réactive pour stocker l'index de la section ouverte dans l'accordéon
  const sectionOpen = ref(1);

  // Crée une référence réactive pour une variable
  const maVar = ref(true);

  // Fonction pour basculer l'état de la section ouverte dans l'accordéon
  const toggleSection = (key) => {
    if (sectionOpen.value === key) {
      sectionOpen.value = null;
    } else {
      sectionOpen.value = key;
    }
  }

  // Données des sections à afficher dans l'accordéon
  const sectionsData = [
    {
      label: 'bouton 1',
      texte: `texte panneau 1 Lorem ipsum dolor sit ame
      consectetur adipisicing elit. Inventore animi dolore,
      rerum magni laudantium quod excepturi laboriosam, 
      ex modi debitis harum reprehenderit eaque quam ut
      ea molestiae. Id, cum dolor!`
    },
    {
      label: 'bouton 2',
      texte: `texte panneau 2 Amet alias provident quos quis, 
      Officia ut ab dolores quos dolorem accusamus ad,
      consectetur unde minima, ipsum eligendi inventore id
      labore, laborum rerum laboriosam corrupti iste.
      Distinctio, perspiciatis!`
    },
    {
      label: 'bouton 3',
      texte: `texte panneau 3 Repudiandae corporis voluptates, 
      odit reprehenderit sint pariatur at voluptatum, cumque
      quia sit eligendi ex culpa eos, alias magnam molestiae
      id modi accusantium ipsa eveniet accusamus. Tempora 
      quis corporis et nam.`
    }
  ]
</script>

<template>
  <!-- Première section statique de l'accordéon -->
  <section>
    <h1 class="font-bold text-2xl mt-3">  Accordeon </h1>
    <button class="btn text-xl" @pointerdown="sectionOpen = 1">Bouton1 </button>
    <p v-show="sectionOpen === 1">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
  </section>

  <!-- Deuxième section statique de l'accordéon -->
  <section>
    <button class="btn text-xl" @pointerdown="sectionOpen = 2">Bouton2 </button>
    <p v-show="sectionOpen === 2">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
  </section>

  <!-- Troisième section statique de l'accordéon -->
  <section>
    <button class="btn text-xl" @pointerdown="sectionOpen = 3">Bouton3 </button>
    <p v-show="sectionOpen === 3">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
  </section>

  <!-- En-tête pour la section bouclée -->
  <h1 class="font-bold text-2xl mt-3"> Section boucle </h1>
  
  <!-- Boucle pour afficher chaque élément de 'sectionsData' -->
  <section v-for="({ label, texte }, key) of sectionsData" :v-key="key">
    <pre class="font-mono">key : {{ key }}</pre>
    <pre class="font-mono">label : {{ label }}</pre>
    <pre class="font-mono">texte : {{ texte }}</pre>
  </section>

  <!-- En-tête pour la section bouclée avec accordéon -->
  <h1 class="font-bold text-2xl mt-3"> Section boucle accordeon </h1>
  
  <!-- Boucle pour afficher chaque élément de 'sectionsData' avec un accordéon -->
  <section class="mt-3" v-for="({ label, texte }, key) of sectionsData" :key="key">
    <button class="btn text-xl font-mono" @click="toggleSection(key)">{{ label }}</button>
    <p class="font-mono" v-show="sectionOpen === key">{{ texte }}</p>
  </section>

  <!-- Bouton pour cacher le contenu -->
  <button @click="maVar = false"> cache  </button>

  <!-- Bouton pour afficher le contenu -->
  <button @click="maVar = true"> pas cache </button>

  <!-- Titre conditionnel basé sur 'maVar' -->
  <h1 v-show="maVar" class="text-2xl">Bonjour monde !</h1>

  <!-- Bouton pour basculer 'maVar' entre true et false -->
  <button @click="maVar = !maVar"> cache ou pas cache  </button>

  <!-- Autre titre conditionnel basé sur 'maVar' -->
  <h1 v-show="maVar" class="text-2xl">Bonjour monde !</h1>

  <!-- Affichage de la valeur de 'maVar' -->
  <p> mavar : {{maVar}} </p>
</template>
