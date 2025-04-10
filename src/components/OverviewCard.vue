<template>
  <div class="overview-card" @click="scrollToStep">
    <div class="icon-wrapper">
      <div class="icon">{{ icon }}</div>
    </div>
    <h3 class="card-title">{{ title }}</h3>
    <p class="card-desc">{{ description }}</p>
  </div>
</template>

<script>
export default {
  name: 'OverviewCard',
  props: {
    icon: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    index: {
      type: Number,
      required: true
    }
  },
  methods: {
    scrollToStep() {
      let stepNumber;
      
      // Map cards to their specific step numbers
      if (this.title === 'Apple Gift Card') {
        stepNumber = 4;
      } else if (this.title === 'ChatGPT App') {
        stepNumber = 5;
      } else {
        // For other cards, use index + 1
        stepNumber = this.index + 1;
      }
      
      const stepElement = document.getElementById(`step-${stepNumber}`);
      
      if (stepElement) {
        // Smooth scroll to the element
        stepElement.scrollIntoView({ behavior: 'smooth' });
      }
    }
  }
}
</script>

<style scoped>
.overview-card {
  background: white;
  padding: 25px 20px;
  border-radius: 12px;
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.06);
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-top: 4px solid var(--primary);
  cursor: pointer; 
  -webkit-tap-highlight-color: rgba(0,0,0,0);
}

.overview-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 20px rgba(0, 0, 0, 0.1);
}

.overview-card:active {
  transform: translateY(-2px);
  box-shadow: 0 8px 15px rgba(0, 0, 0, 0.08);
}

.icon-wrapper {
  background-color: var(--light);
  width: 65px;
  height: 65px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 15px;
}

.icon {
  font-size: 2.2rem;
}

.card-title {
  font-weight: 600;
  margin-bottom: 10px;
  color: var(--dark);
  font-size: 1.1rem;
}

.card-desc {
  color: var(--gray);
  font-size: 0.95rem;
  margin: 0;
  line-height: 1.5;
}

@media (max-width: 768px) {
  .overview-card {
    padding: 20px 15px;
  }
  
  .icon-wrapper {
    width: 55px;
    height: 55px;
    margin-bottom: 12px;
  }
  
  .icon {
    font-size: 1.8rem;
  }
  
  .card-title {
    font-size: 1rem;
  }
  
  .card-desc {
    font-size: 0.9rem;
  }
}

@media (max-width: 480px) {
  .overview-card {
    padding: 18px 12px;
    margin-bottom: 15px;
  }
  
  .icon-wrapper {
    width: 50px;
    height: 50px;
    margin-bottom: 10px;
  }
  
  .icon {
    font-size: 1.6rem;
  }
}
</style> 