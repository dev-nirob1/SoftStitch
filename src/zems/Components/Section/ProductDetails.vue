<script setup>
import ProductGallery from '../Widget/ProductGallery.vue';

</script>

<template>
  <section id="feature" class="product-details bg-light">
    <div class="container">
      <div class="medium-2 gap-2">
        <!-- images based on color changed -->
        <ProductGallery/>
        
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
          <BaseButton class="bg-primary mt-2">Measurement</BaseButton>
        </div>
      </div>
    </div>
  </section>
</template>
<style scoped>
.product-details {
  padding: 3.75rem 0;
  font-size: 1.05rem;
}
</style>
