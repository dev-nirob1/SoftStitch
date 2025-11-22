<script setup>
const features = [
  {
    title: "Super Soft Fabric",
    text: "Crafted for a gentle touch and all-day comfort.",
    image: "https://images.pexels.com/photos/3693235/pexels-photo-3693235.jpeg?_gl=1*1qhu5vs*_ga*OTAzOTgwMTguMTczNzAwNTI1OA..*_ga_8JE65Q40S6*czE3NjM4Mjc4NTUkbzMzJGcxJHQxNzYzODI4NDE4JGoxNCRsMCRoMA.."
  },
  {
    title: "Premium Wool Blend",
    text: "High-quality wool that keeps you warm and stylish.",
    image: "https://images.pexels.com/photos/10474351/pexels-photo-10474351.jpeg?_gl=1*1qgcgt4*_ga*OTAzOTgwMTguMTczNzAwNTI1OA..*_ga_8JE65Q40S6*czE3NjM4Mjc4NTUkbzMzJGcxJHQxNzYzODI3OTQ0JGo1OCRsMCRoMA.."
  },
  {
    title: "Breathable & Warm",
    text: "Stay cozy without overheating.",
    image: "https://images.unsplash.com/photo-1606707951429-5dbb61ab34c2?q=80&w=387&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
  },
  {
    title: "Anti-Shrink Technology",
    text: "Keeps shape and size even after multiple washes.",
    image: "https://images.pexels.com/photos/9462667/pexels-photo-9462667.jpeg?_gl=1*1ly40gv*_ga*OTAzOTgwMTguMTczNzAwNTI1OA..*_ga_8JE65Q40S6*czE3NjM4Mjc4NTUkbzMzJGcxJHQxNzYzODMwMjI1JGoyNCRsMCRoMA.."
  },
  {
    title: "Multiple Colors Available",
    text: "Choose your favorite shades from our collection.",
    image: "https://images.unsplash.com/photo-1674069688221-8f3f7ef6769f?q=80&w=386&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
  },
  {
    title: "Easy Care & Machine Washable",
    text: "Machine washable and easy to maintain without losing shape or softness.",
    image: "https://images.unsplash.com/photo-1626806819282-2c1dc01a5e0c?q=80&w=870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
  },
]
</script>
<template>
  <section class="features">
    <div class="container">
<BaseTitle class="text-center mb-2">Premium Comfort & Quality</BaseTitle>
      <div class="medium-3 gap-2">
        <div v-for="(item, i) in features" :key="i" class="feature-card">
          <div class="image">
            <BaseImage :image="item.image" />
          </div>
          <div class="p-1">
            <SubTitle>{{ item.title }}</SubTitle>
            <BaseParagraph>{{ item.text }}</BaseParagraph>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<style scoped>
.features {
  padding: 3.75rem 0;
}

.feature-card {
  box-shadow: var(--box-shadow);
  border-radius: .5rem;
}

.feature-card .image {
  height: 250px;
  border-radius: .5rem .5rem 0 0;
}

.feature-card p {
  margin-top: .5rem
}

.feature-card .image img {
  border-radius: .5rem .5rem 0 0;
}
</style>
