<script setup>
defineProps({ person: Object, links: Object })
</script>

<template>
  <footer style="padding: 26px 0;">
    <div class="container" style="display:flex; justify-content:space-between; gap:12px; flex-wrap:wrap; color:#d1d5db;">
      <span>© {{ new Date().getFullYear() }} {{ person.name }}</span>
      <div style="display:flex; gap:14px; flex-wrap:wrap;">
        <a :href="links.linkedin" target="_blank" rel="noopener noreferrer">LinkedIn</a>
        <a :href="links.github" target="_blank" rel="noopener noreferrer">GitHub</a>
        <a v-if="links.cvPdf" :href="links.cvPdf" target="_blank" rel="noopener noreferrer">CV</a>
      </div>
    </div>
  </footer>
</template>