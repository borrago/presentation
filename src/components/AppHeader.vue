<script setup>
defineProps({
  person: Object,
  links: Object,
})
</script>

<template>
  <header class="topbar">
    <div class="container topbar-inner">
      <a class="brand" href="#top" aria-label="Voltar ao topo">
        <span class="brand-name">{{ person.name }}</span>
        <span class="brand-role">{{ person.role }}</span>
      </a>

      <nav class="nav">
        <a href="#sobre">Sobre</a>
        <a href="#experiencia">Experiência</a>
        <a href="#projetos">Projetos</a>
        <a href="#contato">Contato</a>
      </nav>

      <div class="actions">
        <a class="btn btn-primary btn-cta" :href="links.whatsapp" target="_blank" rel="noopener noreferrer">
          <span class="ico" aria-hidden="true">
            <svg viewBox="0 0 32 32" width="18" height="18" fill="currentColor">
              <path
                d="M19.11 17.38c-.27-.14-1.58-.78-1.83-.87-.25-.09-.43-.14-.61.14-.18.27-.7.87-.86 1.05-.16.18-.32.2-.59.07-.27-.14-1.15-.42-2.19-1.34-.81-.72-1.36-1.61-1.52-1.88-.16-.27-.02-.42.12-.56.12-.12.27-.32.41-.48.14-.16.18-.27.27-.45.09-.18.05-.34-.02-.48-.07-.14-.61-1.47-.84-2.01-.22-.54-.45-.47-.61-.48h-.52c-.18 0-.48.07-.73.34-.25.27-.95.93-.95 2.27 0 1.34.98 2.63 1.11 2.81.14.18 1.93 2.95 4.67 4.14.65.28 1.15.45 1.55.58.65.21 1.24.18 1.7.11.52-.08 1.58-.65 1.8-1.28.22-.63.22-1.17.16-1.28-.07-.11-.25-.18-.52-.32z"
              />
              <path
                d="M26.67 5.33C23.84 2.49 20.07.93 16.06.93 7.83.93 1.17 7.59 1.17 15.82c0 2.63.69 5.2 2.01 7.47L1 31l7.9-2.07a14.84 14.84 0 0 0 7.16 1.83h.01c8.23 0 14.89-6.66 14.89-14.89 0-4-1.56-7.78-4.29-10.54zm-10.6 22.94h-.01a12.35 12.35 0 0 1-6.3-1.73l-.45-.27-4.69 1.23 1.25-4.57-.29-.47a12.33 12.33 0 0 1-1.88-6.62c0-6.82 5.55-12.37 12.38-12.37 3.3 0 6.4 1.28 8.73 3.61a12.3 12.3 0 0 1 3.62 8.76c0 6.83-5.55 12.37-12.36 12.37z"
              />
            </svg>
          </span>
          WhatsApp
        </a>

        <div class="iconbar">
          <a class="iconbtn" :href="links.linkedin" target="_blank" rel="noopener noreferrer" aria-label="LinkedIn">
            <svg viewBox="0 0 24 24" width="18" height="18" fill="currentColor" aria-hidden="true">
              <path
                d="M20.45 20.45h-3.55v-5.57c0-1.33-.03-3.04-1.85-3.04-1.85 0-2.13 1.45-2.13 2.94v5.67H9.37V9h3.41v1.56h.05c.47-.9 1.63-1.85 3.35-1.85 3.58 0 4.24 2.36 4.24 5.43v6.31zM5.34 7.43a2.06 2.06 0 1 1 0-4.12 2.06 2.06 0 0 1 0 4.12zM7.12 20.45H3.56V9h3.56v11.45zM22.23 0H1.77C.79 0 0 .77 0 1.72v20.56C0 23.23.79 24 1.77 24h20.46c.98 0 1.77-.77 1.77-1.72V1.72C24 .77 23.21 0 22.23 0z"
              />
            </svg>
          </a>

          <a class="iconbtn" :href="links.github" target="_blank" rel="noopener noreferrer" aria-label="GitHub">
            <svg viewBox="0 0 24 24" width="18" height="18" fill="currentColor" aria-hidden="true">
              <path
                d="M12 .5C5.73.5.75 5.48.75 11.76c0 4.93 3.2 9.11 7.64 10.58.56.1.76-.24.76-.54v-2.01c-3.11.68-3.76-1.32-3.76-1.32-.51-1.29-1.24-1.63-1.24-1.63-1.01-.69.08-.68.08-.68 1.12.08 1.71 1.15 1.71 1.15.99 1.69 2.59 1.2 3.22.92.1-.72.39-1.2.7-1.48-2.48-.28-5.09-1.24-5.09-5.52 0-1.22.43-2.22 1.15-3-.12-.28-.5-1.42.11-2.96 0 0 .94-.3 3.08 1.15.89-.25 1.85-.37 2.8-.37.95 0 1.91.12 2.8.37 2.14-1.45 3.08-1.15 3.08-1.15.61 1.54.23 2.68.11 2.96.72.78 1.15 1.78 1.15 3 0 4.29-2.62 5.24-5.12 5.51.4.34.75 1.02.75 2.05v3.04c0 .3.2.65.77.54 4.44-1.47 7.63-5.65 7.63-10.58C23.25 5.48 18.27.5 12 .5z"
              />
            </svg>
          </a>

          <a v-if="links.cvPdf" class="iconbtn" :href="links.cvPdf" target="_blank" rel="noopener noreferrer" aria-label="Baixar CV">
            <svg viewBox="0 0 24 24" width="18" height="18" fill="currentColor" aria-hidden="true">
              <path
                d="M6 2h9l5 5v15a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2zm8 1.5V8h4.5L14 3.5zM12 12a1 1 0 0 1 1 1v3.17l1.59-1.58a1 1 0 1 1 1.41 1.42l-3.3 3.29a1 1 0 0 1-1.4 0l-3.3-3.29a1 1 0 1 1 1.41-1.42L11 16.17V13a1 1 0 0 1 1-1z"
              />
            </svg>
          </a>
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>
.topbar{
  position: sticky;
  top: 0;
  z-index: 50;
  background: rgba(11, 17, 32, 0.78);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(255,255,255,0.06);
}

.topbar-inner{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:16px;
  padding: 12px 0;
}

.brand{
  display:flex;
  flex-direction:column;
  gap:2px;
  min-width: 160px;
}

.brand-name{
  font-weight: 800;
  line-height: 1.05;
}

.brand-role{
  font-size: 0.9rem;
  color: #d1d5db;
  opacity: .9;
}

.nav{
  display:flex;
  gap:18px;
  align-items:center;
  white-space: nowrap;
}

.nav a{
  color: #cbd5e1;
  font-weight: 600;
  opacity: 0.9;
  padding: 8px 10px;
  border-radius: 10px;
}

.nav a:hover{
  opacity: 1;
  background: rgba(255,255,255,0.04);
}

.actions{
  display:flex;
  align-items:center;
  gap:12px;
}

.btn-cta{
  gap: 10px;
  padding: 12px 16px;
}

.ico{
  display:inline-flex;
  align-items:center;
  justify-content:center;
}

.iconbar{
  display:flex;
  gap:10px;
}

.iconbtn{
  display:inline-flex;
  align-items:center;
  justify-content:center;
  width: 42px;
  height: 42px;
  border-radius: 12px;
  border: 1px solid rgba(255,255,255,0.14);
  background: transparent;
  color: #e5e7eb;
  opacity: .95;
  transition: .18s ease;
}

.iconbtn:hover{
  transform: translateY(-1px);
  opacity: 1;
  border-color: rgba(255,255,255,0.22);
  background: rgba(255,255,255,0.04);
}

@media (max-width: 900px){
  .nav{ display:none; }
}

@media (max-width: 520px){
  .iconbar{ display:none; }
  .btn-cta{ padding: 12px 14px; }
}
</style>