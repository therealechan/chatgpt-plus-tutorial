<template>
  <div :id="'step-' + number" class="step">
    <div class="step-number">{{ number }}</div>
    <h3>{{ title }}</h3>
    
    <div class="substeps">
      <div v-for="(substep, index) in substeps" :key="index" class="substep">
        <div class="substep-title">{{ substep.title }}</div>
        <div class="substep-desc" v-html="substep.description"></div>
        <div v-if="substep.hasImage" class="image-wrapper">
          <div class="image-container">
            <img 
              v-if="getImageSrc(substep.title)" 
              :src="getImageSrc(substep.title)" 
              :alt="substep.title" 
              class="screenshot" 
              @click="openModal(getImageSrc(substep.title), substep.title)"
            />
            <div v-else class="image-placeholder">
              [{{ substep.title }} 的截图示意]
            </div>
            <div class="search-icon-wrapper">
              <Search size="18" color="white" />
            </div>
          </div>
          <div class="image-hint">点击图片可查看大图</div>
        </div>
      </div>
    </div>
    
    <div class="tips">
      <div class="tips-title">
        <Lightbulb size="18" class="tips-icon" />
        <span>小贴士</span>
      </div>
      <p>{{ tips }}</p>
    </div>
    
    <!-- Image Modal -->
    <ImageModal 
      :show="showModal" 
      :image-src="modalImageSrc" 
      :image-alt="modalImageAlt"
      @close="closeModal"
    />
  </div>
</template>

<script>
import ImageModal from './ImageModal.vue'
import { Search, Lightbulb } from 'lucide-vue-next'

export default {
  name: 'StepItem',
  components: {
    ImageModal,
    Search,
    Lightbulb
  },
  props: {
    number: {
      type: Number,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    substeps: {
      type: Array,
      required: true
    },
    tips: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      showModal: false,
      modalImageSrc: '',
      modalImageAlt: ''
    }
  },
  methods: {
    getImageSrc(title) {
      const imageMap = {
        '使用 Google 账号登录': '/src/assets/images/screenshots/google-login.jpeg',
        '找到订阅选项': '/src/assets/images/screenshots/upgrade-chatgpt-plus.PNG',
        '完成订阅': '/src/assets/images/screenshots/in-app-purchase.jpg',
        '搜索并下载 ChatGPT': '/src/assets/images/screenshots/AppStore-ChatGPT.jpeg',
        '打开 App Store': '/src/assets/images/screenshots/AppStore-US.jpg',
        '登录 App Store': '/src/assets/images/screenshots/AppStore-US.jpg',
        '兑换礼品卡': '/src/assets/images/screenshots/reddem gitcard.jpeg',
        '切换到美区 Apple ID': '/src/assets/images/screenshots/switch-appstore-id.jpg'
      };
      
      return imageMap[title];
    },
    openModal(src, alt) {
      this.modalImageSrc = src;
      this.modalImageAlt = alt;
      this.showModal = true;
      document.body.style.overflow = 'hidden'; // Prevent scrolling while modal is open
    },
    closeModal() {
      this.showModal = false;
      document.body.style.overflow = ''; // Restore scrolling
    }
  }
}
</script>

<style scoped>
.step {
  background: white;
  border-radius: 12px;
  padding: 30px;
  margin-bottom: 30px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  position: relative;
}

.step-number {
  position: absolute;
  top: -20px;
  left: 30px;
  width: 40px;
  height: 40px;
  background: var(--primary);
  color: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
  font-size: 1.2rem;
  box-shadow: 0 4px 8px rgba(16, 163, 127, 0.3);
}

.step h3 {
  margin-bottom: 20px;
  color: var(--primary);
  font-size: 1.5rem;
}

.substeps {
  margin-left: 20px;
  margin-top: 15px;
}

.substep {
  margin-bottom: 15px;
  position: relative;
  padding-left: 30px;
}

.substep:before {
  content: "";
  position: absolute;
  left: 0;
  top: 8px;
  width: 20px;
  height: 20px;
  background-color: var(--light);
  border-radius: 50%;
  border: 2px solid var(--primary);
}

.substep-title {
  font-weight: 600;
  margin-bottom: 5px;
}

.substep-desc {
  color: var(--gray);
}

.image-wrapper {
  margin: 15px 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.image-container {
  display: flex;
  justify-content: center;
  max-height: 300px;
  overflow: hidden;
  position: relative;
  width: 90%;
}

.search-icon-wrapper {
  position: absolute;
  bottom: 10px;
  right: 10px;
  background-color: rgba(0, 0, 0, 0.6);
  width: 30px;
  height: 30px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.image-container:hover .search-icon-wrapper {
  opacity: 1;
}

.screenshot {
  max-width: 90%;
  max-height: 300px;
  object-fit: contain;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
}

.screenshot:hover {
  transform: scale(1.02);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.image-placeholder {
  width: 100%;
  height: 200px;
  background-color: var(--light-gray);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--gray);
  font-style: italic;
}

.image-hint {
  text-align: center;
  color: var(--gray);
  font-size: 0.8rem;
  margin-top: 5px;
  font-style: italic;
}

.tips {
  background: var(--light);
  border-left: 4px solid var(--primary);
  padding: 15px;
  margin-top: 20px;
  border-radius: 0 8px 8px 0;
}

.tips-title {
  font-weight: 600;
  color: var(--primary);
  margin-bottom: 10px;
  display: flex;
  align-items: center;
}

.tips-icon {
  margin-right: 5px;
  color: var(--primary);
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .image-container {
    max-height: 250px;
  }
  
  .screenshot {
    max-width: 100%;
    max-height: 250px;
  }
  
  .step {
    padding: 20px;
  }
}
</style> 