<script setup>
import { ref } from 'vue';
import TestimonialCard from '../Widget/TestimonialCard.vue';

const testimonials = ref([
  {
    id: 1,
    name: "Sarah Khan",
    role: "University Student",
    review: "SoftStitch sweaters are unbelievably cozy! I wear mine to class every day. The material feels warm without being heavy.",
    avatar: "https://randomuser.me/api/portraits/women/32.jpg"
  },
  {
    id: 2,
    name: "Jahid Hossain",
    role: "Office Worker",
    review: "Perfect balance of comfort and style. I can wear these sweaters at work or on casual outings. The fit is clean and very flattering.",
    avatar: "https://randomuser.me/api/portraits/women/45.jpg"
  },
  {
    id: 3,
    name: "Nabila Rahman",
    role: "Traveler",
    review: "SoftStitch kept me warm during my entire winter trip. Lightweight, soft, and great for layering — easily my favorite travel sweater.",
    avatar: "https://randomuser.me/api/portraits/women/44.jpg"
  },
  {
    id: 4,
    name: "Imran Chowdhury",
    role: "Photographer",
    review: "I’m often outside for long shoots and these sweaters keep me warm without restricting movement. Stylish and incredibly comfortable.",
    avatar: "https://randomuser.me/api/portraits/men/34.jpg"
  },
  {
    id: 5,
    name: "Farzana Ahmed",
    role: "Teacher",
    review: "The knit quality is outstanding. After several washes, the sweater still looks brand new. So soft and perfect for chilly mornings.",
    avatar: "https://randomuser.me/api/portraits/women/52.jpg"
  },
  {
    id: 6,
    name: "Rafiq Karim",
    role: "Software Engineer",
    review: "Soft, breathable, and warm — ideal for long hours at my desk. I bought two more colors because the fit is just that good.",
    avatar: "https://randomuser.me/api/portraits/men/23.jpg"
  },
  {
    id: 7,
    name: "Maya Sultana",
    role: "Fashion Lover",
    review: "The texture and stitching feel premium. I love pairing my SoftStitch sweater with jeans for a clean, modern winter look.",
    avatar: "https://randomuser.me/api/portraits/women/20.jpg"
  },
  {
    id: 8,
    name: "Tanvir Alam",
    role: "Freelancer",
    review: "I’m sensitive to rough fabrics, but this sweater feels incredibly gentle on the skin. Warm enough for winter, comfortable enough for all-day wear.",
    avatar: "https://randomuser.me/api/portraits/men/55.jpg"
  },
  {
    id: 9,
    name: "Samira Niaz",
    role: "Designer",
    review: "The design is minimal and classy. Whether I’m at work or out with friends, this sweater always gets compliments. Amazing quality!",
    avatar: "https://randomuser.me/api/portraits/women/15.jpg"
  }
])


</script>

<template>
  <section id="testimonials" class="testimonials">
    <div class="container">
      <BaseTitle class="text-center mb-2">What Our Clients Say</BaseTitle>

      <div class="card-slider">
        <TestimonialCard v-for="review in testimonials" :review="review" :key="review.id" />
      </div>
      <div class="flex justify-center gap-1">
        <BaseButton class="outline-btn" id="prev">&laquo; Prev</BaseButton>
        <BaseButton class="outline-btn" id="next">Next &raquo;</BaseButton>
      </div>

    </div>
  </section>
</template>
<style scoped>
.testimonials {
  padding: 3.75rem 0;
}

.card-slider {
  position: relative;
  display: flex;
  gap: 2rem;
  transition: transform .5s ease-in-out;
  overflow-x: hidden;
  padding: 1rem 0 2rem 0;
}

.next,
.prev {
  background: var(--white-color);
  border: 1px solid var(--border-color);
  color: var(--light-color);
  padding: .75rem 1rem;
}

.next:hover,
.prev:hover {
  background: var(--secondary-color);
  color: var(--white-color);
  border-color: var(--secondary-color);
}

.next {
  right: 0;
}

.prev {
  left: 0;
}
</style>
