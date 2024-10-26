<script setup>
import HelloWorld from './components/HelloWorld.vue'
import {ref} from 'vue'
import {onMounted} from 'vue'


let count = ref(0); //this is so it updates the website. If it's not here it'll only update in jawa, nut not on the site
let input = ref(" ")
let flowers = ref("rose", "Lily", "Tulip")

function Increment(){
  count.value +=1
}
function Decrease(){
  count.value -=1
}
function Reset(){
  count.value = 0
}
function Addflower(){
  flower.value.push(flowers)
}
</script>

<template>

    <p> Hiiiiiiii. click button :P</p>

    <p>{{ count }}</p>

    <button class="bg-emerald-500" @click="Increment">Make number big >:)</button>
    <button class="bg-red-600"@click="Decrease">Number be small :(</button>
    <button class="bg-stone-700" @click="Reset">Kill the number</button>
    <p></p>
    <p>Did you kill the number?</p>
    <input v-model=" input"/>
    <p>{{ input }}</p>
    

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
