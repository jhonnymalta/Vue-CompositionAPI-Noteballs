<template >
    <div class="text-center mx-auto">
        <div class="bg-teal-500 flex flex-col p-4">
            <label for="" class="text-left" >Title:</label>
            <input v-model="newNotes.title" type="text" class="mb-2" placeholder="Type your title note" />
            <textarea v-model="newNotes.content" ref="newNoteRef" name="" id="" cols="50" rows="5" class="border-2 border-slate-300 mb-2"></textarea>
            <button class="bg-teal-600 text-white disabled:opacity-25" @click="addNote"
            :disabled="!newNotes.title">Add new note</button>
        </div>       
       
        <CardComponent v-for="note in notes" :key="note.id" :note="note" />
            
         
        
       
        
       
        
        
    </div>
       
        
    
</template>
<script setup>
import {reactive, ref} from 'vue'
import CardComponent from '../components/CardComponent.vue';

const notes = ref([])
const newNotes = ref({})
const newNoteRef = ref(null)

const addNote = () =>{       
    notes.value.unshift(newNotes)
    
    
    newNoteRef.value.focus()
    console.log(notes)
}

</script>