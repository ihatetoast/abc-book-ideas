<script setup>
import AppHeader from './components/AppHeader.vue'
import EntryForm from './components/EntryForm.vue'
import FilterBar from './components/FilterBar.vue'
import CardList from './components/CardList.vue'
</script>

<template>
  <AppHeader />
  <main>
    <EntryForm />
    <FilterBar />
    <CardList />
  </main>
</template>
