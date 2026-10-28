<script setup>
import { ref, computed } from 'vue'
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
  { id: 4, letter: 'G', soundNote: 'hard g', word: 'gibbon', themes: ['animals'] },
  { id: 5, letter: 'G', soundNote: 'hard g', word: 'guava', themes: ['food'] },
  { id: 6, letter: 'G', soundNote: 'soft g, sounds like j', word: 'gelato', themes: ['food'] },
])

const themeFilter = ref('')
const letterFilter = ref('')

const usedLetters = computed(() => [...new Set(entries.value.map((e) => e.letter))].sort())

const filteredEntries = computed(() =>
  entries.value.filter((e) => {
    const themeMatch = !themeFilter.value || e.themes.includes(themeFilter.value)
    const letterMatch = !letterFilter.value || e.letter === letterFilter.value
    return themeMatch && letterMatch
  }),
)
</script>

<template>
  <AppHeader />
  <main>
    <EntryForm />
    <FilterBar
      v-model:theme="themeFilter"
      v-model:letter="letterFilter"
      :themes="existingThemes"
      :letters="usedLetters"
    />
    <CardList :entries="filteredEntries" />
  </main>
</template>
