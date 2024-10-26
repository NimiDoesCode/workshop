<script setup>
import HelloWorld from './components/HelloWorld.vue'
import {ref} from 'vue'
import {onMounted} from 'vue'
import PocketBase from 'pocketbase';

const titleVal = ref(" ")
const descVal = ref(" ")
const nameVal = ref(" ")

const db = new PocketBase('http://127.0.0.1:8090');
const posts = ref([])


async function submit(){

  const record = {
    title: titleVal.value,
    desc: descVal.value,
    name: nameVal.value,
    };

   await db.collection("test").create(record);
   posts.value.push(record);
}

onMounted(async()=>{
  const result = await db.collection("test").getFullList();
  posts.value = result
})
</script>

<template>

 <input v-model="titleVal" />
 <button @click = "submit">Submit</button>

 <ul>
  <li v-for="item in posts">
    {{ item.title }} {{ item.desc }}
  </li>
 </ul>

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
