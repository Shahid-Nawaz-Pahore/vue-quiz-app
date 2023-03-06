<script setup>
import q from './data/quizes.json';
</script>

<template>
  <div class="container">
    {{ q }}
    <header>
      <h1>quizes</h1> 
      <input type="text" placeholder="Please search here...">
    </header>
    <div class="options-container">
      <div class="card">
        <img src="https://marvel-b1-cdn.bc0a.com/f00000000026007/resilienteducator.com/wp-content/uploads/2012/11/AdobeStock_60467600_cup.jpg" alt="subject image">
        <div class="card-text">
          <h2>Math</h2>
          <p>5 Qustions</p>
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