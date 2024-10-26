<script setup>
import HelloWorld from './components/HelloWorld.vue'
import {ref} from 'vue'
import {onMounted} from 'vue'
import PocketBase from 'pocketbase';


</script>

<template>

 
 <button class= "bg-pink-300 text-white rounded border-zinc-600 border-2 active:bg-violet-700 px-2"@click = "submit">Subscribe</button>


</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
