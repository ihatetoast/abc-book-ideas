<script setup>
import { ref } from 'vue'
import AppHeader from './components/AppHeader.vue'
import EntryForm from './components/EntryForm.vue'
import FilterBar from './components/FilterBar.vue'
import CardList from './components/CardList.vue'

const existingThemes = ref(['animals', 'food', 'plants'])

// fake data before db
// note on letters: Use caps and lower case here bc using digraphs like gh, ch, sh, ...
const entries = ref([
  { id: 1, letter: 'A', soundNote: '', word: 'armadillo', themes: ['animals'] },
  { id: 2, letter: 'Ch', soundNote: '', word: 'cherry', themes: ['food', 'plants'] },
  { id: 3, letter: 'G', soundNote: 'soft g, sounds like j', word: 'giraffe', themes: ['animals'] },
])
</script>

<template>
  <AppHeader />
  <main>
    <EntryForm />
    <FilterBar />
    <CardList :entries="entries" />
  </main>
</template>
