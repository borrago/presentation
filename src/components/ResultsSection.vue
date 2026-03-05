<script setup>
defineProps({ results: Object })
</script>

<template>
  <section id="resultados" class="section">
    <div class="container">
      <h2>{{ results.title }}</h2>

      <div class="grid cards-2">
        <div class="card">
          <h3>Impacto</h3>
          <ul>
            <li v-for="(r, idx) in results.items" :key="idx">{{ r }}</li>
          </ul>
        </div>

        <div class="card">
          <h3>Resumo</h3>
          <p style="color: var(--muted); line-height: 1.85; margin: 0;">
            Resultados focados em performance, estabilidade e sistemas de grande porte.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>