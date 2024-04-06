<script setup>
import { ref } from "vue";
import SingleNote from '../components/Notes/SingleNote.vue';
const notes = ref([
  { id: 1, content: "first note" },
  { id: 2, content: "second note" },
]);
const newNoteRef = ref(null);
const newNote = ref("");
const addNote = () => {
  const currentDate = new Date().getTime();
  const note = {
    id:Math.floor(Math.random()*10),
    content: newNote.value
  }
  notes.value.unshift(note);
  newNote.value = '';
  newNoteRef.value.focus();
};
const DeleteNote = (id) => {
  notes.value=notes.value.filter((note)=>note.id !== id)
}
</script>

<template>
  <div class="has-background-info-dark my-4 p-4">
    <div class="field">
      <label class="label has-text-primary-100">Note</label>
      <div class="control">
        <textarea
          class="textarea"
          placeholder="Add New Note"
          v-model="newNote" ref="newNoteRef"
        ></textarea>
      </div>
    </div>

    <div class="field is-grouped is-grouped-right">
      <div class="control">
        <button  :disabled="!newNote" class="button is-link" @click.prevent="addNote">
          New Notes
        </button>
      </div>
    </div>
  </div>
   <div class="card mb-4" v-for="note in notes" :key="note.id">
     <SingleNote :note="note" @onDeleteNote="DeleteNote"/>

   </div>
</template>
