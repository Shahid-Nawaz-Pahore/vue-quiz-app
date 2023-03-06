<script setup>
import q from './data/quizes.json';
import {ref , watch} from 'vue';
import Card from './components/Quiz-Card.vue'
const quizes = ref(q)
const search = ref("")
watch(search, ()=>{
quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()))
})
</script>

<template>
  <div class="container">
    <!-- {{ quizes}} -->
    <header>
      <h1>quizes</h1> 
      <input v-model.trim="search" type="text" placeholder="Please search here...">
    </header>
    <div class="options-container">
      <Card/>
      <!-- <div v-for="quiz in quizes" :key="quiz.iq" class="card">
        <img  :src="quiz.img" a lt="subject image">
        <div class="card-text">
          <h2>{{ quiz.name }}</h2>
          <p>{{quiz.questions.length}} Qustions</p>
        </div>
      </div> -->
    </div>
  </div>
</template>

<style scoped>
.container{
  width: 1000px;
margin: auto;
  
}
header{
  margin-bottom: 10px;
  margin-top: 30px;
  display: flex;
  align-items: center;
}
header h1{
  font-weight:bold ;
  margin-right: 30px;
}
header input{
background-color: azure;
border-radius: 5px;
border: none;
}
.options-container{
  display: flex;
  flex-wrap: wrap;
  margin-top: 40px;
}
/* card style */

</style>