<template>
  <ul>
      <li v-for="(note, index) in notes" :key="index" class="border w-max mx-auto p-2">
          {{ note }}
      </li>
  </ul>

  <input type="text" v-model="title" @keypress.enter="save" class="border rounded-sm mt-3">
  <p>Total Notes: {{totalNotes}}</p>
</template>

<script>
import { ref, computed } from '@vue/reactivity'
import { useStore } from 'vuex'

export default {
    setup() {
        const store = useStore()
        const notes = computed(() => store.state.notes)
        const totalNotes = computed(() => store.getters.totalNotes)
        const title = ref('')
        
        

        function save() {
            store.dispatch('saveNote', title.value)
            title.value = ""
        }

        return {
            notes,
            title,
            totalNotes,
            save
        }
    }

}
</script>

<style>

</style>