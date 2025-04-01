<template>
  <div class="overview">
    <OverviewCard 
      v-for="(card, index) in cards" 
      :key="index"
      :icon="card.icon"
      :title="card.title"
      :description="card.description"
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
  display: flex;
  justify-content: space-between;
  margin-bottom: 40px;
  flex-wrap: wrap;
}
</style> 