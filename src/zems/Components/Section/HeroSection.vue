<template>
  <section class="hero">
    <div class="container">
        <div class="content">
        <HeroTitle>Soft. Stylish. <br> Winter-Ready.</HeroTitle>
        <BaseParagraph>
          Discover premium-quality sweaters designed for comfort and crafted for everyday elegance.
        </BaseParagraph>
        <div class="flex gap-1">
          <BaseButton class="outline-btn">Explore Features</BaseButton>
          <BaseButton class="bg-primary">Buy Now</BaseButton>
        </div>
      </div>
    </div>
  </section>
</template>
<style scoped>
.hero {
  min-height: 100vh;
  background: url('/hero.jpg') no-repeat center / cover ;
}
@media(min-width: 768px){
  .hero .content{
    padding-top: 12rem;
    max-width: 45%;
  font-size: 1.1rem;
}
}
</style>
