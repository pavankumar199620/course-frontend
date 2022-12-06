<template>
    
    <div class="title">
        
        <div v-for="course in courses" :key="course.id" >
            <Course :course="course"/>
     
               
                
                
        
        </div>
       
    </div>

</template>

<script>

import Course from './Course.vue'
export default{

    name: 'Coursebox',
    components: {
        Course
    },
    props: {
        courses: Array
    }
}

</script>

<style scoped>

.course{

    background-color:#030508;
    padding: 1em;
    color: rgb(243, 129, 227);
}

</style>
