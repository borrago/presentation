<script setup>
defineProps({ education: Object })
</script>

<template>
  <section id="formacoes" class="section section-alt">
    <div class="container">
      <h2>{{ education.title }}</h2>

      <div class="grid cards-2">
        <div v-for="(e, idx) in education.items" :key="idx" class="card">
          <h3 style="margin:0 0 6px;">{{ e.title }}</h3>
          <p style="margin:0; color: var(--muted); line-height: 1.75;">
            {{ e.institution }}
          </p>
          <p v-if="e.period" style="margin: 10px 0 0; color: var(--accent); font-weight: 600;">
            {{ e.period }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>