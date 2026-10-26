<script setup>
defineProps({ entries: Array })
</script>

<template>
  <section>
    <ul>
      <li v-for="entry in entries" :key="entry.id">
        <p>{{ entry.letter }} is for {{ entry.word }}</p>
        <p v-if="entry.soundNote">{{ entry.soundNote }}</p>
        <ul>
          <li v-for="theme in entry.themes" :key="theme">{{ theme }}</li>
        </ul>
      </li>
    </ul>
  </section>
</template>
