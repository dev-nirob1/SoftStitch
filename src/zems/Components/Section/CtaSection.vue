<script setup>
defineProps({
  handleOpenFormModal: {
    type: Function
  }
})
</script>

<template>
  <section class="cta-section relative mt-5">
    <div class="container large-2 gap-2">
      <div class="cta-content">
        <BaseTitle>Wrap Yourself in Soft Comfort</BaseTitle>
        <BaseParagraph>
          Discover premium knit sweaters designed for warmth, style, and everyday comfort.
        </BaseParagraph>
        <div class="flex align-center gap-1 mb-1">
          <h4>৳1490</h4>
          <span class="text-secondary">20% OFF</span>
        </div>
        <BaseButton @click="handleOpenFormModal" class="outline-btn">
          Shop Now
        </BaseButton>
      </div>
      <div class="image">
        <BaseImage image="/cta-3.png" />
      </div>
    </div>

  </section>
</template>
<style scoped>
.cta-section {
  padding: 8rem 0;
  background: var(--dark-color);
  color: var(--white-color);
}

.btn {
  color: var(--white-color);
  border-color: var(--white-color)
}

.cta-content {
  font-size: 1.1rem;
}

.cta-section p {
  margin: .5rem 0;
}

.outline-btn:hover {
  border-color: var(--primary-color);
}

@media (min-width: 992px) {
  .image {
    position: absolute;
    right: 0;
    height: 560px;
    bottom: 0;
    max-width: 50%;
  }

  img {
    object-fit: cover;
  }
}
</style>
