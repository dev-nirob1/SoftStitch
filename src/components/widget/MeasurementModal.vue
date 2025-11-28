<script setup>
defineProps({
  isModalOpen: {
    type: Boolean
  },
  handleCloseModal: {
    type: Function
  }
})
</script>

<template>
  <div v-if="isModalOpen" class="measuremnt-modal flex-center">

    <div class="modal-content">
      <BaseButton @click="handleCloseModal" class="close-btn"><i class="fa-solid fa-x"></i></BaseButton>
      <div class="image">
        <BaseImage image="/measurement.png" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.measuremnt-modal {
  position: fixed;
  inset: 0;
  z-index: 1000;
}

.measuremnt-modal::before {
  content: "";
  position: absolute;
  inset: 0;
  background: rgb(0, 0, 0, .7);
}

.modal-content {
  position: relative;
  height: 70vh;
  width: 80%;
  aspect-ratio: 16 / 9;
  border-radius: 1rem;
  overflow: hidden;
  box-shadow: var(--box-shadow);
  z-index: 1;
}

.close-btn {
  position: absolute;
  top: 0;
  right: 0.5rem;
  background: var(--secondary-color);
  border: none;
  color: var(--white-color);
  padding: 0.5rem .75rem;
  border-radius: 0.25rem;
  cursor: pointer;
  z-index: 1000;
}

.measuremnt-modal img {
  object-fit: contain;
}

@media (min-width: 768px) {
  .modal-content {
    height: 80vh;
    width: 60vw;
  }
}
</style>
