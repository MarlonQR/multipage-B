<script setup>
import { ref } from 'vue';



const name = "espaiderman"
let counter = ref(5)
let characters = ref([])

function add() {
    counter.value++
    console.log(counter)
    characters.value.push(counter.value)
}
function less() {
    counter.value--
    console.log(counter)
}
</script>

<template>
    <div class="mx-auto max-w-96 rounded py-4 px-6 bg-gradient-to-r from-orange-400 to-rose-600  ">
        Hola {{ name }}
        <div v-if="counter > 0" class="flex items-center  justify-center  bg-red-600 text-white rounded-full size-8">
            {{ counter }}

        </div>

        <div v-else>
            Nadie te escribe :(
        </div>
        <div @click="add"
            class="flex items-center  justify-center  bg-green-600 text-white rounded-full size-8 cursor-pointer hover:bg-green-400">
            +

        </div>
        <div @click="less"
            class="flex items-center  justify-center  bg-blue-600 text-white rounded-full size-8 cursor-pointer hover:bg-blue-400">
            -

        </div>

    </div>
    <div 
    v-for="(name, index) in characters" :key="index" 
    class="bg-rose-500 mb-1"
    >
        {{ name }}

    </div>

</template>