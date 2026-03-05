<script setup>
defineProps({ highlights: Object })
</script>

<template>
  <section id="diferenciais" class="section">
    <div class="container">
      <h2>{{ highlights.title }}</h2>
      <div class="tags">
        <span v-for="(t, idx) in highlights.tags" :key="idx">{{ t }}</span>
      </div>
    </div>
  </section>
</template>