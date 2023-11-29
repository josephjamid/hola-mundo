<script setup>
const props = defineProps(
  {
    tarea :{
      type:String,

      default: 'tarea por defecto'
    },
    index: {
    type: Number

  }

  }

  
)
const emit = defineEmits(['borrarHijo'])
function borrar (index){
   // console.log('borrar hijo', index)
   emit('borrarHijo' ,index)


}

</script>

<template>
    

    <div class="flex justify-between px-4 py-1 mt-1 text-black bg-gray-200 rounded">
      {{ props.tarea }}
      <span @click="borrar(props.index)" class=" px-2 transition-colors hover:cursor-pointer hover:bg-red-800 rounded-l-none  text-center text-white bg-red-600 rounded">X</span>
    </div>
  
</template>