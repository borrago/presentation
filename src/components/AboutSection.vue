<script setup>
defineProps({ about: Object })
</script>

<template>
  <section id="sobre" class="section">
    <div class="container">
      <h2>{{ about.title }}</h2>
      <p class="section-text">{{ about.text }}</p>
    </div>
  </section>
</template>