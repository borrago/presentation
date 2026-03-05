<script setup>
defineProps({ projects: Object })
</script>

<template>
  <section id="projetos" class="section section-alt">
    <div class="container">
      <h2>{{ projects.title }}</h2>

      <div class="grid cards-2">
        <article v-for="(p, idx) in projects.items" :key="idx" class="card">
          <h3>{{ p.name }}</h3>

          <p style="margin: 0 0 12px; color: #d1d5db; line-height: 1.7; max-width: 72ch;">
            {{ p.subtitle }}
          </p>

          <ul style="margin: 0; padding-left: 18px; line-height: 1.85;">
            <li v-for="(b, i) in p.bullets" :key="i">{{ b }}</li>
          </ul>

          <div class="tags" style="margin-top: 14px;">
            <span v-for="(t, i) in p.stack" :key="i">{{ t }}</span>
          </div>

          <div style="display: flex; gap: 10px; flex-wrap: wrap; margin-top: 16px;">
            <a v-if="p.repo" class="btn btn-secondary" :href="p.repo" target="_blank" rel="noopener noreferrer">Repo</a>
            <a v-if="p.demo" class="btn btn-primary" :href="p.demo" target="_blank" rel="noopener noreferrer">Demo</a>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>