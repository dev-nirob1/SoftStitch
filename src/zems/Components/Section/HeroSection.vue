<script setup>
defineProps({
  handleOpenFormModal: {
    type: Function
  }
})
</script>

<template>
  <section class="hero text-white relative">
    <div class="container">
      <div class="medium-2  gap-2">
        <div class="content">
          <HeroTitle>Soft. Stylish. <br> Winter-Ready.</HeroTitle>
          <BaseParagraph>Stay warm in premium-crafted sweaters designed for everyday comfort.
          </BaseParagraph>
          <div class="flex gap-1">
            <BaseButton @click="handleOpenFormModal" class="bg-primary">Buy Now</BaseButton>
            <a class="btn outline-btn" href="#feature">Explore Feature</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<style scoped>
.hero {
  min-height: 120vh;
  display: flex;
  align-items: center;
  font-size: 1.1rem;
  background: url('/hero.png') no-repeat center /cover;
}

.image img {
  position: absolute;
  bottom: 0;
  height: 450px;
  width: 450px;
}
.outline-btn {
  border-color: var(--white-color);
  color: var(--white-color);
}
.outline-btn:hover{
  border-color: var(--primary-color);
}
</style>

