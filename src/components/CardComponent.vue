<template>
        <div class="bg-white rounded overflow-hidden shadow-lg my-4 ">
            
            <div class="px-6 py-4">
                <div class="text-teal-500 font-bold text-xl mb-2 text-left">{{note.title}}</div>
                <p class="text-gray-700 text-base">
                {{note.content}}
                </p>
            </div>
            <div class="text-right">
                <span class="mr-2 text-gray-300">{{ characterLengh }} character</span>

            </div>
            <div class=" pt-4 pb-2 text-right">
                <a href="" class="bg-teal-500  hover:bg-teal-400 py-2 px-4 text-white">Edit</a>
                <a href="" class="bg-teal-500 hover:bg-teal-400 py-2 px-4 text-white">Delete</a>
            </div>
           
        </div>    
</template>

<script setup>
import { computed} from 'vue'

const props = defineProps({
    note:{
        type: Object,
        required: true
    }
})

const characterLengh = computed(()=>{
    return props.note.content.length
}

)

</script>