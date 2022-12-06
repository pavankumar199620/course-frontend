<template>
  <div class="container">
    <!-- #3 must use the component-->
    <Myheader mytitle="Courses" 
      aboutpage ="Course Titles" />
    
    <Coursebox :courses = "courses"/>
    <About aboutme="About" />
    



  </div>
</template>
<script>



//import HelloWorld from './components/HelloWorld.vue'
// 1
import Myheader from './components/Myheader.vue'
import About from './components/About.vue'
// ----import Bookbox from './components/Bookbox.vue'
import Coursebox from './components/Coursebox.vue'


// data url: http://localhost:5555/books , this might be different for you
export default {
  name: 'App',
  components: {
    // 2 register the component 
    Myheader,
    Coursebox,
    About
  },

  data(){
    return {
      courses: []
    }
  },
  methods: {
    // promises

      async fetchCourses(){
         const res= await fetch('https://pavan.herokuapp.com/db.json')
         const data= await res.json()
          console.log(data)
         return data
      }

  },

  async created(){
    this.courses = await this.fetchCourses()
  }
}
</script>










<style>




@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
  background-color: #e6efda;
}
.container {
  max-width: 400px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid rgb(15, 5, 5);
  padding: 30px;
  border-radius: 5px;
  background-color: lightsalmon;
}

div{
  margin-bottom: 0.5em;
}



</style>


