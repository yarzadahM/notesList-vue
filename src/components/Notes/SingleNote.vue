<script setup>
import { computed } from "vue";

const props = defineProps({
  note: {
    type: Object,
    required: true,
  },
});
const emit=defineEmits(['onDeleteNote'])
const characterLength = computed(() => {
  const noteLength = props.note.content.length;
  const des=noteLength > 1 ?'characters' :'character'
  return `${props.note.content.length}  ${des}`;
});

const onDeleteNote = () => {
  emit('onDeleteNote',props.note.id)
}
</script>
<template>
  <div class="card-content">
    <div class="content">
      {{ note.content }}
      <div class="has-text-right">
        <small>{{ characterLength }} </small>
      </div>
    </div>
  </div>
  <footer class="card-footer">
    <a href="#" class="card-footer-item">Edit</a>
    <a href="#" class="card-footer-item" @click.prevent="onDeleteNote">Delete</a>
  </footer>
</template>
