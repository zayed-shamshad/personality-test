<script >
    export default {
        name: 'homeview',
    }

</script>

<template>
  <div class="home">
    <button @click="$router.push('quiz')" class="quiz">
      Take the quiz !
    </button>
    <img src="../assets/man thinking.svg" :height="300" >
    <!-- <div class="innerbox">
      <div class="inner"></div>
      <div class="inner"></div>
      <div class="inner"></div>
    </div> -->

  </div>
</template>
<style >
  .home {
   width:100vw;
   height:85vh;
   background-color:#05386B;
   display:flex;
   justify-content:center;
   align-items:center;
   flex-direction: column;
  }
  .innerbox {
      height: 60vh;
      width: 90vw;
      background-color: rgb(0, 255, 229);
      flex-direction: row;
      display: flex;
      justify-content: center;
      align-items: flex-end;
    }
  
    .inner {
      position: relative;
      height: 30vh;
      width: 20vw;
      background-color: black;
      margin: 15px;
  
    }
.quiz{
  background-color:#EDF5E1;
  border: none;
  border-radius: 10px;
  padding: 10px;
  font-size: 20px;
  font-weight: bold;
  margin: 10px;
  cursor: pointer;
  COLOR: #05386B;
  transition: all 0.2s ease-in-out;
}
.quiz:hover{
  transform:scale(1.1)
}
</style>