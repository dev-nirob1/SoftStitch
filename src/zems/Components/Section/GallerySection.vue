<script setup>
import ImageViewerModal from '@/components/widget/ImageViewerModal.vue';
import { computed, ref } from 'vue';

const images = ref([
  {
    id: 1,
    image: '/red-sweater.png'
  },
  {
    id: 2,
    image: '/white-sweater.png'
  },
  {
    id: 3,
    image: '/yellow-sweater.png'
  },
  {
    id: 4,
    image: '/blue-sweater.png'
  },
  {
    id: 5,
    image: '/blue-back.png'
  },
  {
    id: 6,
    image: 'https://images.pexels.com/photos/6995719/pexels-photo-6995719.jpeg?_gl=1*1cfagdg*_ga*OTAzOTgwMTguMTczNzAwNTI1OA..*_ga_8JE65Q40S6*czE3NjM4Mjc4NTUkbzMzJGcxJHQxNzYzODMyMTczJGo1OSRsMCRoMA..'
  },
])

const isModalOpen = ref(false)
const selectedIndex = ref(0)

// open modal
const handleOpenModal = (imageIndex) => {
  isModalOpen.value = true;
  selectedIndex.value = imageIndex;
}

// image select
const selectedImage = computed(() => {
  return images.value[selectedIndex.value].image
});

// close modal
const handleCloseModal = () => {
  isModalOpen.value = false;
}

// handle prev button
const handlePrev = () => {
  if (selectedIndex.value > 0) {
    selectedIndex.value -= 1;
  }
}

// handle next button
const handleNext = () => {
  selectedIndex.value += 1;
  if (selectedIndex.value === images.value.length) {
    selectedIndex.value = 0;
  }
}


</script>

<template>
  <section id="gallery" class="gallery">
    <!-- :selectedImage="selectedImage" -->
    <ImageViewerModal :isModalOpen="isModalOpen" :handleCloseModal="handleCloseModal" :selectedImage="selectedImage"
      :handleNext="handleNext" :handlePrev="handlePrev" />

    <div class="container">
      <BaseTitle class="text-center mb-2">Sweater Showcase</BaseTitle>
      <div class="medium-3 gap-2">

        <div v-for="(img, i) in images" :key="img.id" @click="handleOpenModal(i)" class="image">
          <BaseImage :image="img.image" />
        </div>
      </div>
    </div>


  </section>
</template>

<style scoped>
.gallery {
  padding: 3.75rem 0;
}

.gallery .image {
  position: relative;
  max-height: 350px;
  border-radius: .5rem;
  overflow: hidden;
  cursor: pointer;
}

.gallery .image::after {
  content: '+';
  display: grid;
  place-content: center;
  font-size: 3rem;
  position: absolute;
  inset: 0;
  opacity: 0;
  transition: all .3s ease-in-out;
}

.image:hover::after {
  background: rgba(0, 0, 0, 0.3);
  opacity: 1;
  color: var(--white-color);
}
</style>
