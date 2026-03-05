<script setup>
import { cv } from './data/cv'

import AppHeader from './components/AppHeader.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import StackSection from './components/StackSection.vue'
import ExperienceSection from './components/ExperienceSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import HighlightsSection from './components/HighlightsSection.vue'
import ResultsSection from './components/ResultsSection.vue'
import EducationSection from './components/EducationSection.vue'
import ContactSection from './components/ContactSection.vue'
import AppFooter from './components/AppFooter.vue'
</script>

<template>
  <div class="page">
    <AppHeader :person="cv.person" :links="cv.links" />

    <HeroSection
      :person="cv.person"
      :links="cv.links"
      :quick-summary="cv.quickSummary"
      :highlights-top="cv.highlightsTop"
    />

    <main>
      <AboutSection :about="cv.about" />
      <StackSection :stack="cv.stack" />
      <ExperienceSection :experience="cv.experience" />
      <ProjectsSection :projects="cv.projects" />
      <HighlightsSection :highlights="cv.highlights" />
      <ResultsSection :results="cv.results" />
      <EducationSection :education="cv.education" />
      <ContactSection :contact="cv.contact" />
    </main>

    <AppFooter :person="cv.person" :links="cv.links" />
  </div>
</template>