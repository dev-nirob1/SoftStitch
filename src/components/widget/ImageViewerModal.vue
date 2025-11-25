<script setup>
defineProps({
  isModalOpen: {
    type: Boolean
  },
  handleModalOpen: {
    type: Function
  },
  handleCloseModal: {
    type: Function
  },
  selectedImage: {
    type: Object
  },
  handlePrevImage: {
    type: Function
  },
  handleNextImage: {
    type: Function
  },
})
</script>

<template>
  <div v-if="isModalOpen" class="modal">
    <div class="modal-content flex-center">
      <!-- Navigation Buttons -->
      <BaseButton @click="handlePrevImage" class="btn-prev">
        <i class="fa-solid fa-arrow-left"></i>
      </BaseButton>
      <BaseButton @click="handleNextImage" class="btn-next">
        <i class="fa-solid fa-arrow-right"></i>
      </BaseButton>

      <!-- modal content -->
      <div class="modal-details">
        <div class="image">
          <BaseImage :image="selectedImage.image" />
        </div>
      </div>

      <!-- Close Button -->
      <BaseButton @click="handleCloseModal" class="close-btn">
        <i class="fa-solid fa-xmark"></i>
      </BaseButton>
    </div>
  </div>
</template>

<style>
.modal {
  position: relative;
}

.modal .modal-content {
  position: fixed;
  top: 0;
  left: 0;
  min-height: 100vh;
  width: 100vw;
  overflow-y: scroll;
  background-color: rgba(0, 0, 0, 0.9);
  z-index: 999;
}

.modal .btn {
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  color: var(--white-color);
  border-radius: .25rem;
  border: none;
}

.modal .btn-prev,
.modal .btn-next {
  top: 50%;
  transform: translateY(-50%);
}

.modal .btn-prev {
  left: 1rem;
}

.modal .btn-next {
  right: 1rem;
}

.modal .close-btn {
  position: fixed;
  top: 1rem;
  right: 1rem;
}

.modal .modal-details {
  height: 70vh;
  width: 80vw;
}

.modal .image img {
  object-fit: contain;
}

@media (min-width: 768px) {
  .modal .modal-details {
    height: 80vh;
    width: 60vw;
  }
}
</style>
