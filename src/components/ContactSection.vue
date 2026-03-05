<script setup>
defineProps({ contact: Object })
</script>

<template>
  <section id="contato" class="section section-alt">
    <div class="container">
      <h2>{{ contact.title }}</h2>
      <div class="contact-box">
        <p>
          <strong>Telefone:</strong>
          <a :href="contact.whatsappUrl" target="_blank" rel="noopener noreferrer">{{ contact.phone }}</a>
        </p>
        <p><strong>E-mail:</strong> {{ contact.emailText }}</p>
        <p><strong>Localização:</strong> {{ contact.location }}</p>
      </div>
    </div>
  </section>
</template>