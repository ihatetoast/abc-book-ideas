<script setup>
defineProps({ themes: Array, letters: Array })
const theme = defineModel('theme')
const letter = defineModel('letter')
</script>

<template>
  <section>
    <label for="theme-filter">Theme</label>
    <select id="theme-filter" v-model="theme">
      <option value="">All themes</option>
      <option v-for="t in themes" :key="t" :value="t">{{ t }}</option>
    </select>

    <label for="letter-filter">Letter</label>
    <select id="letter-filter" v-model="letter">
      <option value="">All letters</option>
      <option v-for="l in letters" :key="l" :value="l">{{ l }}</option>
    </select>
  </section>
</template>
