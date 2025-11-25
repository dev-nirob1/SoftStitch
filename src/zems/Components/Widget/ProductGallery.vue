<script setup>
import { ref } from 'vue';

const images = [
  {
    id: 1,
    image: "/red.jpg",
    color: { name: "Red", hex: "#D86A6A" }
  },
  {
    id: 2,
    image: "https://images.unsplash.com/photo-1616646068304-53bcead13c58?q=80&w=870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
    color: { name: "Yellow", hex: "#F6D26C" }
  },
  {
    id: 3,
    image: "https://images.unsplash.com/photo-1542595607-63507592a7d8?q=80&w=387&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
    color: { name: "White", hex: "#fff" }
  },
];

const selectedImage = ref(images[0])
const handleActiveImage = (item) => {
  selectedImage.value = item;
}

</script>


<template>
  <section class="gallery">
    <div class="active-image">

      <BaseImage :image="selectedImage.image" />

    </div>
    <div class="thumbs mt-1">
      <div v-for="(item) in images" :key="item.id" @click="handleActiveImage(item)" class="color-list">
        <div :style="{ 'background': item.color.hex }" class="color" :class="{ 'active': selectedImage.id == item.id }">
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.gallery {
  margin-bottom: 2rem;
}

.color {
  height: 2rem;
  width: 2rem;
  border-radius: 50%;
  cursor: pointer;
}

.color.active {
  border: 2px solid var(--dark-color);
}


.gallery .active-image img {
  width: 100%;
  height: 100%;
}

.gallery .thumbs {
  display: flex;
  justify-content: center;
  gap: .75rem;
}

.gallery .thumbs .active-thumb {
  border: 3px solid var(--primary-color);
}

.gallery .thumbs img {
  width: 60px;
  height: 60px;
  object-fit: cover;
  cursor: pointer;
}

@media (min-width: 768px) {

  .gallery .active-image {
    height: 400px;
  }

  .gallery .thumbs img {
    width: 80px;
    height: 80px;
  }

}
</style>
