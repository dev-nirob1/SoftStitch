<template>
  <section class="hero text-white relative">
    <div class="container">
      <div class="medium-2  gap-2">
        <div class="content">
          <HeroTitle>Soft. Stylish. <br> Winter-Ready.</HeroTitle>
          <BaseParagraph>Discover premium-quality sweaters designed for comfort and crafted for everyday elegance.
          </BaseParagraph>
          <div class="flex gap-1">
            <a class="btn bg-primary" href="#feature">Explore Feature</a>
            <BaseButton class="outline-btn">Buy Now</BaseButton>
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
</style>

