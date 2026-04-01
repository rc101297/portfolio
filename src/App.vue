<template>
  <div>
    <NavigationBar />
    <HeroSection />
    <AboutSection id="about" />
    <TechStack id="tech-stack" />
    <ProjectsSection id="projects" />
    <FeatureSection />
    <ContactSection id="contact" />
    <FooterSection />
  </div>
</template>

<script setup>
import NavigationBar from './components/NavigationBar.vue';
import HeroSection from './components/HeroSection.vue';
import AboutSection from './components/AboutSection.vue';
import TechStack from './components/TechStack.vue';
import ProjectsSection from './components/ProjectsSection.vue';
import FeatureSection from './components/FeatureSection.vue';
import ContactSection from './components/ContactSection.vue';
import FooterSection from './components/FooterSection.vue';
</script>

<style>
body {
  margin: 0;
}
</style>
