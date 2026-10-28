<script setup>
defineProps({ entries: Array, theme: String, letter: String })

// TODO: computed emptyMessage:
//   theme + letter -> "There are no {letter}s for {theme}"
//   theme only     -> "{theme} doesn't have any cards yet" + hint to the form
//   neither        -> "No cards yet" + hint to the form
// TODO: template: v-if entries.length -> list, v-else -> <p>{{ emptyMessage }}</p>
</script>

<template>
  <section>
    <ul>
      <li v-for="entry in entries" :key="entry.id">
        <p>{{ entry.letter }} is for {{ entry.word }}</p>
        <p v-if="entry.soundNote">{{ entry.soundNote }}</p>
        <ul>
          <li v-for="pill in entry.themes" :key="pill">{{ pill }}</li>
        </ul>
      </li>
    </ul>
  </section>
</template>
