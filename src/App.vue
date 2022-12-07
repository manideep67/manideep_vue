<template>
  <div class="container">
    <HeaderTop TitleName="TOP POPULATED CITIES IN THE WORLD"  />
    <div class="About">
    <h1> <button><a href="https://manideepcharugundla.herokuapp.com/"> About Me </a></button> </h1>
    </div>
    <PopulationBox :population="population"  />
    
  </div>
</template>
<script>
import HeaderTop from './components/Header.vue'
import PopulationBox from './components/PopulationBox.vue'
export default {
  name: 'App',
  components: {
    HeaderTop,
    PopulationBox
  },
  data(){
    return {
      population: []
    }
  },
  methods: {
      async fetchpopulation(){
        const res= await fetch('https://manideepcharugundla.herokuapp.com/api')
         const data= await res.json()
          console.log(data)
         return data.population
      }

  },
async created(){
    this.population = await this.fetchpopulation()
  }
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0px;
}
body {
  font-family: 'Montserrat', sans-serif;
}
.container {
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 40px;
  border-radius: 5px;
  width:100%;
  background-color: rgb(11, 11, 11);
  

}
div{
  margin-bottom: 0.5em;
  padding:10px;
}
.About{
  width:100%;
}
a{
    text-decoration: none;
    color: rgb(2, 7, 16);
}
button{
    font-size:30px;
    font-family:'Times New Roman', Times, serif;
    background-color: rgb(193, 218, 224);
    width:100%;
    border:3px solid rgb(46, 99, 173);
}
</style>