<script setup>
defineProps({
  isFormModalOpen: {
    type: Boolean
  },
  handleCloseFormModal: {
    type: Function
  }
})
const handleSubmit = () => {
  alert('Thanks For Message!')
}
</script>

<template>
  <div v-if="isFormModalOpen" class="video-modal flex-center">

    <div class="modal-content">
      <BaseButton @click="handleCloseFormModal" class="video-close"><i class="fa-solid fa-x"></i></BaseButton>

      <form @submit.prevent="handleSubmit">
        <div class="medium-2 align-center gap-1">
          <label>
            <InputField type="text" placeholder="Enter Your Name" required />
          </label>
          <label>
            <InputField type="email" placeholder="Enter Your Email" required />
          </label>
        </div>

        <div class="medium-2 gap-1">
          <label>
            <InputField type="number" placeholder="Enter Your number" required />
          </label>
          <label>
            <InputField type="text" placeholder="Enter Your Address" required />
          </label>
        </div>
        <div class="medium-2 gap-1">
          <label>
            <InputField type="number" placeholder="Quantity" required />
          </label>
          <label>
            <select>
              <option disabled selected>Delivery Method</option>
              <option>Cash On Delivery</option>
              <option>Home Delivery</option>
            </select>
          </label>
        </div>
        <div>
          <BaseTextArea placeholder="Special Instruction" />
        </div>
        <BaseButton class="bg-secondary mb-2">Order Now</BaseButton>
      </form>

    </div>
  </div>
</template>

<style scoped>
.video-modal {
  position: fixed;
  inset: 0;
  z-index: 1000;
}

.video-modal::before {
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
  overflow-y: scroll;
  box-shadow: var(--box-shadow);
  z-index: 1;
  background: var(--white-color);
  padding: 2rem 0;
}

.modal-content::-webkit-scrollbar {
  display: none;
  /* Chrome, Safari */
}

form {
  padding: 2rem;
  border-radius: 1rem;
  height: 100%;
}

form input {
  padding: 1rem;
  border-radius: 1.5rem;
}

select {
  border-radius: 1.5rem;
}

.video-close {
  position: fixed;
  top: 2rem;
  right: 2rem;
  background: var(--secondary-color);
  border: none;
  color: var(--white-color);
  padding: 0.5rem .75rem;
  border-radius: 0.25rem;
  cursor: pointer;
  z-index: 1000;
  display: grid;
  place-content: center;
}

@media (min-width: 768px) {
  .modal-content {
    height: 80vh;
    width: 60vw;
  }
}
</style>
