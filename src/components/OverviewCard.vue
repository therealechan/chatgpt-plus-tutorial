<template>
  <div class="overview-card">
    <div class="icon">{{ icon }}</div>
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
    }
  }
}
</script>

<style scoped>
.overview-card {
  flex-basis: calc(25% - 20px);
  min-width: 200px;
  background: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  margin-bottom: 20px;
  text-align: center;
  transition: transform 0.3s ease;
}

.overview-card:hover {
  transform: translateY(-5px);
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
}
</style> 