<template>
   
    <div>
       <h2>{{course.Coursetitle}}</h2>
       <h4>{{course.Description}}</h4>
       <h4>{{course.Published}}</h4>
       <h4>{{course.Cost}}</h4>
       <h4>{{course.Duration}} </h4>
    </div>
   
   
   
</template>

<script>

export default{
    name: 'Course',
    props:{
        course: Array
    }
   
}
</script>

<style scoped>

h4{
    margin: 2px;
}


div{
    background-color: lightgreen;
    color: #030d15;
    padding: 1em;
}



</style>