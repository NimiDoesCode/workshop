<script setup>
import HelloWorld from './components/HelloWorld.vue'
import {ref} from 'vue'
import {onMounted} from 'vue'

let prayerTimes = ref([])

onMounted(async function() {
  let response = await fetch ('https://www.e-solat.gov.my/index.php?r=esolatApi/TakwimSolat&period=week&zone=WLY01')
  let data = await response.json()
  prayerTimes.value = data.prayerTime
  consolse.log(data.prayerTime)
})
</script>

<template>
  <div v-for="time in prayerTimes">
    <p  class="text-xl, bg-slate-400">date: {{ time.hijri}}</p>
    <p  class="text-xl, bg-slate-400">date: {{ time.date }}</p>
    <p  class="text-xl">day: {{ time.day }}</p>
    <p  class="text-xl">imsak: {{ time.imsak }}</p>
    <p  class="text-xl">fajr: {{ time.fajr }}</p>
    <p  class="text-xl">syuruk: {{ time.syuruk }}</p>
    <p  class="text-xl">dhuhr: {{ time.dhuhr }}</p>
    <p  class="text-xl">asr: {{ time.asr }}</p>
    <p  class="text-xl">maghrib: {{ time.maghrib }}</p>
    <p  class="text-xl">isha: {{ time.isha }}</p>

  </div>
  <p v-for="_ in 5">try</p>
   
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
