<template>
  <div v-if="show" class="image-modal-overlay" @click="closeModal">
    <div class="image-modal-content" @click.stop>
      <img :src="imageSrc" :alt="imageAlt" class="modal-image" />
      <button class="close-button" @click="closeModal">
        <X size="24" />
      </button>
    </div>
  </div>
</template>

<script>
import { X } from 'lucide-vue-next'

export default {
  name: 'ImageModal',
  components: {
    X
  },
  props: {
    show: {
      type: Boolean,
      required: true
    },
    imageSrc: {
      type: String,
      required: true
    },
    imageAlt: {
      type: String,
      default: '图片'
    }
  },
  methods: {
    closeModal() {
      this.$emit('close');
    }
  }
}
</script>

<style scoped>
.image-modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.7);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
  padding: 20px;
  animation: fadeIn 0.2s ease-in-out;
  -webkit-tap-highlight-color: transparent;
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

.image-modal-content {
  position: relative;
  max-width: 90%;
  max-height: 90%;
  background-color: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.3);
}

.modal-image {
  display: block;
  max-width: 100%;
  max-height: 80vh;
  object-fit: contain;
}

.close-button {
  position: absolute;
  top: 15px;
  right: 15px;
  width: 40px;
  height: 40px;
  background-color: rgba(0, 0, 0, 0.6);
  color: white;
  border: none;
  border-radius: 50%;
  font-size: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: background-color 0.2s;
  touch-action: manipulation;
}

.close-button:hover {
  background-color: rgba(0, 0, 0, 0.8);
}

/* Mobile responsiveness */
@media (max-width: 768px) {
  .image-modal-overlay {
    padding: 15px;
  }
  
  .image-modal-content {
    max-width: 95%;
    max-height: 95%;
  }
  
  .modal-image {
    max-height: 85vh;
  }
  
  .close-button {
    top: 10px;
    right: 10px;
    width: 36px;
    height: 36px;
  }
}

@media (max-width: 480px) {
  .image-modal-overlay {
    padding: 10px;
  }
  
  .image-modal-content {
    max-width: 98%;
  }
  
  .close-button {
    top: 8px;
    right: 8px;
    width: 32px;
    height: 32px;
  }
}
</style> 