<template>
  <section class="cta-section relative mt-5">
    <div class="container medium-2 gap-2">
      <div class="cta-content">
        <BaseTitle>Wrap Yourself in Soft Comfort</BaseTitle>
        <BaseParagraph>
          Discover premium knit sweaters designed for warmth, style, and everyday comfort.
        </BaseParagraph>
        <BaseButton class="outline-btn">
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
  background: var(--primary-color);
  /* background: url('/cta.jpg') center / cover */
}
.btn{color:var(--white-color);border-color:var(--white-color)}
.cta-content {
  /* max-width: 50%; */
  font-size: 1.1rem;
}
.image {
  position: absolute;
  right: 2rem;
  height: 500px;
  bottom: 0;
  max-width: 50%;
}
img {object-fit: contain}
</style>
