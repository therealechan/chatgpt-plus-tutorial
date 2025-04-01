<template>
  <div class="overview-card" @click="scrollToSection" role="button" tabindex="0" @keyup.enter="scrollToSection">
    <div class="icon">{{ icon }}</div>
    <h3 class="card-title">{{ title }}</h3>
    <p class="card-desc">{{ description }}</p>
    <div class="view-section">查看详情 ↓</div>
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
    scrollToSection() {
      const targetSection = document.getElementById(`step-${this.index + 1}`);
      if (targetSection) {
        targetSection.scrollIntoView({ behavior: 'smooth', block: 'start' });
      }
    }
  }
}
</script>

<style scoped>
.overview-card {
  background: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  cursor: pointer;
}

.overview-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.12);
}

.overview-card:focus {
  outline: 2px solid var(--primary);
  outline-offset: 2px;
}

.icon {
  font-size: 2.5rem;
  margin-bottom: 15px;
  color: var(--primary);
}

.card-title {
  font-weight: 600;
  margin-bottom: 10px;
  color: var(--dark);
}

.card-desc {
  color: var(--gray);
  font-size: 0.9rem;
  margin: 0;
}

.view-section {
  color: var(--primary);
  font-size: 0.8rem;
  margin-top: 10px;
  font-weight: 500;
  opacity: 0.7;
  transition: opacity 0.3s ease;
}

.overview-card:hover .view-section {
  opacity: 1;
}
</style> 