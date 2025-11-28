<script setup>
import { ref } from 'vue';
import ProductGallery from '../Widget/ProductGallery.vue';
import MeasurementModal from '@/components/widget/MeasurementModal.vue';

const isModalOpen = ref(false)

// openModal
const handleModalOpen = () => {
  isModalOpen.value = true
}
// closeModal
const handleCloseModal = () => {
  isModalOpen.value = false
}
</script>

<template>
  <section id="feature" class="product-details bg-light">
    <div class="container">
      <div class="medium-2 gap-2">
        <!-- images based on color changed -->
        <ProductGallery />

        <!-- details  -->
        <div class="project-details">
          <BaseTitle class="mb-1">Wrap Yourself in Comfort</BaseTitle>
          <BaseParagraph>
            Experience unbeatable softness with our premium winter sweater — designed for warmth, comfort, and style.
          </BaseParagraph>

          <BaseParagraph>
            From the rooftop infinity pool to lush garden lounges, every detail reflects comfort and
            sophistication. </BaseParagraph>

          <ul class="all-2 gap-1">
            <ListItem><i class="fas fa-wind"></i> Breathable & Warm</ListItem>
            <ListItem><i class="fas fa-feather"></i> Ultra Soft Texture</ListItem>
            <ListItem><i class="fas fa-tint"></i> Machine Washable</ListItem>
            <ListItem><i class="fas fa-layer-group"></i> Premium Wool Blend</ListItem>
          </ul>
          <BaseButton @click="handleModalOpen" class="bg-primary mt-2">Measurement</BaseButton>
        </div>
      </div>
    </div>

    <MeasurementModal :isModalOpen="isModalOpen" :handleCloseModal="handleCloseModal"/>
  </section>
</template>
<style scoped>
.product-details {
  padding: 3.75rem 0;
  font-size: 1.05rem;
}
.product-details li {
  background: var(--white-color);
  padding: .5rem;
  border-radius: .5rem;
}
.product-details li i {
  color: var(--secondary-color);
}
</style>
