<script setup lang="ts">
import { onErrorCaptured, ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router/auto'
const menuIsOpen = ref(false)

onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})
</script>

<template>

         

  <header>
    <nav>
      <ul>
        <li>
          <RouterLink to="/" class="text-red-500 underline"> Accueil </RouterLink></li>
          <li>
          <RouterLink to="/" class="text-red-500 underline"> Accordeon </RouterLink>
        </li>
        <li>
          <RouterLink to="/" class="text-red-500 underline"> A propos </RouterLink>
        </li>
      </ul>
    </nav>

    <button
    aria-controls="mainNav"
    aria-expanded="true"
    class="rounded-full border-2 border-purple-600 bg-purple-300 px-5 text-2xl "
    @pointerdown="menuIsOpen = !menuIsOpen"
  >
    menu
  </button>
  <!-- nav#mainNav>ul>li*3>a[href="#"]{item $} -->
  <Transition
    class="transition-transform duration-1000"
    enter-from-class="-translate-x-full"
    enter-to-class="translate-x-0"
    leave-active-class="-translate-x-full"
  >
  <nav id="mainNav"  v-show="menuIsOpen" class="bg-blue-500 w-64 py-4 px-2" >
    <ul>
      <li><a href="#" class="text-white font-bold" >item 1</a></li>
      <li><a href="#" class="text-white font-bold">item 2</a></li>
      <li><a href="#" class="text-white font-bold">item 3</a></li>
    </ul>
  </nav>
</Transition>
  </header>
  
  <RouterView v-slot="{ Component }">
    <Suspense>
      <component :is="Component" />
    </Suspense>
  </RouterView>
</template>
