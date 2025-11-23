<script setup>
import { ref } from 'vue';

const images = [
  {
    image: "/red.jpg",
    color: { name: "Red", hex: "#D86A6A" }
  },
  {
    image: "https://tunatheme.com/tf/html/quarter-preview/quarter/img/img-slide/31.jpg",
    color: { name: "Yellow", hex: "#F6D26C" }
  },
  {
    image: "https://tunatheme.com/tf/html/quarter-preview/quarter/img/img-slide/33.jpg",
    color: { name: "White", hex: "#F5F1EB" }
  },
  {
    image: "https://tunatheme.com/tf/html/quarter-preview/quarter/img/img-slide/34.jpg",
    color: { name: "Gray", hex: "#D8D8D8" }
  }
];


const activeImage = ref(images[0])
const handleChangeImage = (item) => {
  activeImage.value = images[item] ;
  console.log(item);
}

</script>


<template>
  <section class="gallery">
    <div class="active-image">
      <BaseImage :image="activeImage.image" />
    </div>
    <div class="thumbs mt-1">
      <div v-for="(item, i) in images" :key="i" class="color-list">
        <div @click="handleChangeImage(i)" :style="{ 'background': item.color.hex }" class="color active"></div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.gallery {
  margin-bottom: 2rem;
}

.color {
  height: 1.5rem;
  width: 1.5rem;
  border-radius: 50%;
}

.color.active {
  border: 2px solid var(--dark-color);
}

.gallery .active-image {
  width: 100%;
  height: 280px;
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
