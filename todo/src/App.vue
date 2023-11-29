<script setup>

import TaskComponent from'@/components/TaskComponent.vue' 
import {ref} from 'vue'
const tareas = ref (["ninguna ", " dormir ", " descansar"])
function deleteTask (index){
  tareas.value.splice(index, 1)
 
}

</script>

<template>
  <div class=" mt-12 px-4 w-96 py-2 bg-gray-50  shadow-md rounded mx-auto">
    <h1 class="text-2x1 font-semibold text-center">lista de tareas</h1>

    <div class="flex mt-2">
      <input type="text" class=" outline-none rounded-r-none w-4/5 h-8 px-2 py-1 border border-green-600 rounded">
      <span class="  transition-colors hover:cursor-pointer hover:bg-green-800 rounded-l-none w-1/5 h-8 text-xl font-bold text-center text-white bg-green-600 rounded">
        +
      </span>
    </div>


  <TaskComponent  v-for="(tarea,index) in tareas" :key="index" :tarea="tarea" :index="index" @borrarHijo="deleteTask" />
 
  </div>
</template>


