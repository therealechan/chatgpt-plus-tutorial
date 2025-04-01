<template>
  <div class="overview">
    <OverviewCard 
      v-for="(card, index) in cards" 
      :key="index"
      :icon="card.icon"
      :title="card.title"
      :description="card.description"
      :index="index"
    />
  </div>
</template>

<script>
import OverviewCard from './OverviewCard.vue'

export default {
  name: 'OverviewSection',
  components: {
    OverviewCard
  },
  data() {
    return {
      cards: [
        {
          icon: '🇺🇸',
          title: '美国区 Apple ID',
          description: '用于下载 ChatGPT App'
        },
        {
          icon: '🔒',
          title: '美国线路 VPN',
          description: '用于访问和注册 ChatGPT'
        },
        {
          icon: '💳',
          title: 'Apple Gift Card',
          description: '用于充值美元到 Apple ID'
        },
        {
          icon: '✨',
          title: 'ChatGPT App',
          description: '在应用内完成 Plus 订阅'
        }
      ]
    }
  }
}
</script>

<style scoped>
.overview {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  margin: 40px auto;
  max-width: 1200px;
  padding: 0 20px;
}

@media (min-width: 768px) {
  .overview {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .overview {
    grid-template-columns: repeat(4, 1fr);
  }
}
</style> 