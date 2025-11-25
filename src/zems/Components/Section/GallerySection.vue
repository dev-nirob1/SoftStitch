<script setup>
import ImageViewerModal from '@/components/widget/imageViewerModal.vue';
import { ref } from 'vue';

const images = ref([
  {
    id: 1,
    image: 'https://images.unsplash.com/photo-1687275161342-8699c61e4364?q=80&w=464&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
  },
  {
    id: 2,
    image: 'https://images.unsplash.com/photo-1687275160744-6cb5bb16544a?q=80&w=464&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
  },
  {
    id: 3,
    image: 'https://images.unsplash.com/photo-1641399050826-9616c90427bb?q=80&w=580&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
  },
  {
    id: 4,
    image: 'https://images.pexels.com/photos/2971061/pexels-photo-2971061.jpeg?_gl=1*xmznkl*_ga*OTAzOTgwMTguMTczNzAwNTI1OA..*_ga_8JE65Q40S6*czE3NjM4Mjc4NTUkbzMzJGcxJHQxNzYzODMxOTI1JGoxJGwwJGgw'
  },
  {
    id: 5,
    image: 'https://images.pexels.com/photos/5490059/pexels-photo-5490059.jpeg?_gl=1*1jjqf7t*_ga*OTAzOTgwMTguMTczNzAwNTI1OA..*_ga_8JE65Q40S6*czE3NjM4Mjc4NTUkbzMzJGcxJHQxNzYzODMyMDU3JGoyMCRsMCRoMA..'
  },
  {
    id: 6,
    image: 'https://images.pexels.com/photos/6995719/pexels-photo-6995719.jpeg?_gl=1*1cfagdg*_ga*OTAzOTgwMTguMTczNzAwNTI1OA..*_ga_8JE65Q40S6*czE3NjM4Mjc4NTUkbzMzJGcxJHQxNzYzODMyMTczJGo1OSRsMCRoMA..'
  },
])

// modal logic
const isModalOpen = ref(false)
const selectedIndex = ref(0)

const handleOpenModal = (imageIndex) => {
  isModalOpen.value = true
  // console.log('index', imageIndex);
  selectedIndex.value = imageIndex;
  // console.log('selected',selectedIndex, 'clicked', imageIndex);
}
const handleCloseModal = () => {
  isModalOpen.value = false
}
const handlePrev = () => {
  if (selectedIndex.value > 0) {
    selectedIndex.value -= 1;
  }
}
const handleNext = () => {
  selectedIndex.value += 1;
  if (selectedIndex.value === images.value.length) {
    selectedIndex.value = 0;
    // console.log('selected ', selectedIndex);
  }
}
</script>

<template>
  <section id="gallery" class="gallery">
    <div class="container">
      <BaseTitle class=" text-center mb-2">Sweater Showcase</BaseTitle>
      <div class="medium-3  gap-2">

        <div v-for="(img, i) in images" :key="img.id" @click="handleOpenModal(i)" class="image">
          <BaseImage :image="img.image" />
        </div>
      </div>
    </div>
    <ImageViewerModal class="modal" :isModalOpen="isModalOpen" :handleCloseModal="handleCloseModal"
      :handleNext="handleNext" :handlePrev="handlePrev">
      <div class="image">
        <BaseImage :image="images[selectedIndex].image" :alt="images[selectedIndex].alt" />
      </div>
    </ImageViewerModal>
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
