<script setup>
import {ref} from "@vue/reactivity";
import CountdownTimer from "./components/CountdownTimer.vue";

const days = ref();
const hours = ref();
const minuts =ref();
const seconds =ref();
const started = ref(false)



const vale = ref(Date.now() + 10*60*60*1000);


function startTimer(){
started.value =true;
value.value =Date.now()
+(days.value || 0) * 3600000 *24
+(hours.value || 0) * 3600000 
+(minutes.value || 0) * 60000

}

function resetTimer(){
  started.value = false;
  value.value =0;
  days.value = null;
  hours.value = null;
  minutes.value =null;
  seconds.value = null;
}



</script>

<template>
  <div class="countdown-inputs">
    <input type="number" min="0" v-model="days" placeholder="Days">
    <input type="number" min="0" v-model="hours" placeholder="Hours">
    <input type="number" min="0" v-model="minutes" placeholder="Minutes">
    <input type="number" min="0" v-model="seconds" placeholder="Seconds">
    <div class="countdown-buttons">
      <button @click="startTimer">Start</button>
      <button v-if="started" @click="resetTimer">Reset</button>
      <countdown-timer v-if="started" :date="value"/>
    </div>
  </div>
  

  
  
</template>

<style scoped>
.countdown-inputs,
.countdown-buttons {
  display: flex;
  justify-content: center;
  margin-bottom: 1rem;
}
.countdown-inputs>input {
width: 68px;
margin: 0 0.25;
}
</style>
