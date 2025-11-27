<script setup>
import { ref } from 'vue';
import FooterSection from './components/section/FooterSection.vue';
import NavbarSection from './components/section/NavbarSection.vue';
import CtaSection from './zems/Components/Section/CtaSection.vue';
// import FaqSection from './zems/Components/Section/FaqSection.vue';
import FeatureSection from './zems/Components/Section/FeatureSection.vue';
import GallerySection from './zems/Components/Section/GallerySection.vue';
import HeroSection from './zems/Components/Section/HeroSection.vue';
import ProductDetails from './zems/Components/Section/ProductDetails.vue';
import TestimonialSection from './zems/Components/Section/TestimonialSection.vue';
import FormModal from './components/widget/FormModal.vue';

const isFormModalOpen = ref(false)
// form popup logic

const handleOpenFormModal = () => {
  isFormModalOpen.value = true
}
const handleCloseFormModal = () => {
  isFormModalOpen.value = false
}
</script>

<template>
  <NavbarSection :handleOpenFormModal="handleOpenFormModal" />
  <HeroSection :handleOpenFormModal="handleOpenFormModal" />
  <FeatureSection />
  <ProductDetails />
  <GallerySection />
  <CtaSection :handleOpenFormModal="handleOpenFormModal" />
  <TestimonialSection />
  <!-- <FaqSection/> -->
  <FooterSection />

  <FormModal :isFormModalOpen="isFormModalOpen" :handleCloseFormModal="handleCloseFormModal"/>
</template>

<style scoped></style>
