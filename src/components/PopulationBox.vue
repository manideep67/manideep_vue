<template>
    <div class="populationbox">
       <div v-for="population in population" :key="population.id" >
               <PopulaTion :population="population"/>
       </div>
    </div>
</template>
<script>
import PopulaTion from "./Population.vue"
export default{
   name: 'PopulationBox',
   components: {
      PopulaTion
   },
   props: {
    population: Array
   }
}
</script>
<style>
.populationbox{
   padding: 40px;
   display: grid;
   grid-template-columns: 1fr 1fr 1fr;
   border:3px solid rgb(11, 12, 97);
   background-repeat: no-repeat;
   background-attachment: fixed;  
   background-size: cover;
   background-image: url("https://ourworldindata.org/uploads/2019/10/Screen-Shot-2019-10-31-at-12.02.19-768x527.png");
}
</style>