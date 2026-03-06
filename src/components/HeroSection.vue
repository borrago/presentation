<script setup>
import avatar from '../assets/avatar.jpg'

defineProps({
  person: Object,
  links: Object,
  quickSummary: Array,
  highlightsTop: Array,
})
</script>

<template>
  <header id="top" class="hero">
    <div class="container hero-content">
      <div class="hero-text">
        <div class="title-row">
          <img class="avatar" :src="avatar" alt="Foto de perfil" />
          <div class="title-text">
            <p class="eyebrow">{{ person.role }}</p>
            <h1>{{ person.name }}</h1>
          </div>
        </div>

        <p class="subtitle">{{ person.headline }}</p>
        <p class="description">{{ person.summary }}</p>

        <div class="hero-actions">
          <a :href="links.whatsapp" target="_blank" rel="noopener noreferrer" class="btn btn-primary">
            Falar no WhatsApp
          </a>
          <a href="#projetos" class="btn btn-secondary">
            Ver projetos
          </a>
        </div>

        <div class="kpi-grid" v-if="highlightsTop?.length">
          <div class="kpi" v-for="(k, idx) in highlightsTop" :key="idx">
            <span class="kpi-label">{{ k.label }}</span>
            <span class="kpi-value">{{ k.value }}</span>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>
.hero{
  background:
    radial-gradient(circle at 75% 10%, rgba(59,130,246,.22), transparent 38%),
    radial-gradient(circle at 15% 80%, rgba(37,99,235,.14), transparent 40%),
    linear-gradient(135deg, #0b1120, #111827 60%, #0f172a);
  padding: 84px 0 64px;
  border-bottom: 1px solid rgba(255,255,255,.06);
}

.hero-content{
  display: grid;
  grid-template-columns: 1fr; /* single-column hero (como no print) */
  gap: 28px;
}

.hero-text{
  max-width: 920px; /* evita texto espalhado demais */
}

.eyebrow{
  margin: 0 0 10px;
  font-size: .85rem;
  text-transform: uppercase;
  letter-spacing: .18em;
  color: #93c5fd;
}

h1{
  margin: 0;
  font-size: clamp(2.6rem, 5vw, 4.6rem);
  line-height: 1.03;
}

.subtitle{
  margin: 14px 0 0;
  font-size: 1.05rem;
  color: #cbd5e1;
  text-transform: uppercase;
  letter-spacing: .04em;
}

.description{
  margin: 18px 0 0;
  font-size: 1rem;
  line-height: 1.85;
  color: #d1d5db;
  max-width: 76ch;
}

/* Ações */
.hero-actions{
  display:flex;
  gap: 12px;
  flex-wrap: wrap;
  margin-top: 22px;
}

.btn{
  padding: 12px 18px;
  border-radius: 14px;
}

/* KPIs */
.kpi-grid{
  display:grid;
  grid-template-columns: repeat(3, minmax(0, 240px));
  gap: 12px;
  margin-top: 22px;
}

.kpi{
  border: 1px solid rgba(255,255,255,.10);
  background: rgba(255,255,255,.03);
  border-radius: 16px;
  padding: 14px;
  box-shadow: 0 10px 26px rgba(0,0,0,.18);
}

.kpi-label{
  display:block;
  color: #cbd5e1;
  font-size: .88rem;
  opacity: .9;
}

.kpi-value{
  display:block;
  margin-top: 6px;
  font-weight: 850;
  font-size: 1.05rem;
  color: #e5e7eb;
}

.title-row{
  display: flex;
  align-items: center;
  gap: 16px;
  margin-bottom: 10px;
}

.title-text{
  display: flex;
  flex-direction: column;
  gap: 6px;
}

/* avatar ao lado do nome */
.avatar{
  width: 120px;
  height: 120px;
  border-radius: 999px;
  object-fit: cover;
  border: 1px solid rgba(255,255,255,.12);
  box-shadow:
    0 12px 28px rgba(0,0,0,.35),
    0 0 0 6px rgba(37,99,235,.10);
  margin: 0;
}

/* no mobile, empilha (fica mais elegante em telas pequenas) */
@media (max-width: 520px){
  .title-row{
    align-items: flex-start;
    gap: 12px;
  }
}

/* Mobile */
@media (max-width: 900px){
  .hero{ padding: 64px 0 52px; }
  .kpi-grid{ grid-template-columns: 1fr; max-width: 420px; }
}

@media (max-width: 600px){
  .btn{ width: 100%; }
}
</style>