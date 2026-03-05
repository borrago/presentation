<script setup>
defineProps({ stack: Object })
</script>

<template>
  <section id="stack" class="section section-alt">
    <div class="container">
      <h2>{{ stack.title }}</h2>

      <div class="skills-grid">
        <div v-for="(c, idx) in stack.cards" :key="idx" class="card">
          <h3>{{ c.title }}</h3>

          <div class="tags" style="margin-top: 10px;">
            <span v-for="(t, i) in c.tags" :key="i">{{ t }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* 2 colunas = 2 em 2 */
.skills-grid{
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 20px;
}

.card{
  height: 100%;
}

/* responsivo: 1 coluna no mobile */
@media (max-width: 900px){
  .skills-grid{
    grid-template-columns: 1fr;
  }
}
</style>