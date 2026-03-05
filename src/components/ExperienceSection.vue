<script setup>
defineProps({ experience: Object })
</script>

<template>
  <section id="experiencia" class="section">
    <div class="container">
      <h2>{{ experience.title }}</h2>

      <div class="timeline">
        <div v-for="(item, idx) in experience.items" :key="idx" class="timeline-item">
          <div class="timeline-header">
            <h3>{{ item.company }}</h3>
            <span>{{ item.period }}</span>
          </div>
          <p class="role">{{ item.role }}</p>
          <ul>
            <li v-for="(b, i) in item.bullets" :key="i">{{ b }}</li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>