<template>

 <v-card
    :loading="loading"
    class="mx-auto my-12"
    max-width="374"
    
  >
  <v-container fluid >
  <v-card-title class="stringtitle"> STRING MANIPULATOR</v-card-title>

   <v-text-field label="Enter a String" v-model="stringInput"></v-text-field>

   

   <v-btn class="v-btn" block color="primary"
     elevation="9"
     small
     x-large
     x-small
     @click="doCountVowel">Get Result</v-btn>

   
     <p></p>
  <br>
  <br>
  <br>
     <p> Count Vowel</p>
   {{vowelCount}}
    <p> Count Constant /s</p>
   {{consCount}}
    <p> Count Numbers</p>
   {{numCount}}
    <p> Vowel Conversion to (*)</p>
   {{convert}}
   </v-container>
 </v-card>  

</template>

<script setup>
import {ref} from 'vue'

const stringInput = ref('')
const vowelCount = ref(0)
const consCount = ref(0)
const numCount = ref(0)
const convert = ref(0)

function doCountVowel () {
     vowelCount.value = stringInput.value.match(/[aeiou]/gi).length;
     consCount.value = stringInput.value.match(/[bcdfghjklmnpqrstvwxys]/gi).length;
     numCount.value = stringInput.value.match(/[0123456789]/ig).length;
     convert.value = stringInput.value.replace(/[aeiou]/gi, '*')
     return vowelCount.value; 
}

</script>

<style>
.stringtitle {
  text-align: center;
 
  background-image: url('https://i.imgur.com/yGmrlyg.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  border-top: solid 1em #1d2920;

  color: #0c972a;
}

.v-btn {
     color: aquamarine;
}
</style>
