<script setup>
import q from './data/quizes.json';
import {ref , watch} from 'vue';
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
      <div v-for="quiz in quizes" :key="quiz.iq" class="card">
        <img  :src="quiz.img" a lt="subject image">
        <div class="card-text">
          <h2>{{ quiz.name }}</h2>
          <p>{{quiz.questions.length}} Qustions</p>
        </div>
      </div>
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
.card{
width: 310px;
overflow: hidden;
border-radius:2% ;
box-shadow: 1px 1px 10px rgb(0, 0,0,0, 1);
margin-bottom: 35px;
margin-right: 20px;
cursor: pointer;
}
.card img{
 width: 100%;
 height: 190px;
 margin: 0;
}
.card .card-text{
  padding: 0 5px;
}
.card .card-text h2{
  font-weight: bold;
}


</style>