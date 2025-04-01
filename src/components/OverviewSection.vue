<template>
  <section class="overview-section">
    <h2 class="section-title">订阅所需的准备工作</h2>
    
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
    
    <div class="overview-description">
      <p>成功订阅 ChatGPT Plus 需要完成上述四个核心步骤。本教程将详细指导您如何准备美区 Apple ID、设置 VPN、获取 Apple Gift Card，以及完成 ChatGPT Plus 的订阅流程。整个过程约需花费 $20 美元（约 ¥145 元人民币），订阅成功后您将获得优先使用权、更快的响应速度以及新功能的提前访问权限。</p>
    </div>
  </section>
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
.overview-section {
  margin: 40px auto;
  max-width: 1200px;
  padding: 0 20px;
}

.section-title {
  text-align: center;
  margin-bottom: 30px;
  color: var(--dark);
  font-size: 1.8rem;
  position: relative;
  padding-bottom: 10px;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 80px;
  height: 3px;
  background: linear-gradient(90deg, var(--primary), var(--secondary));
  border-radius: 3px;
}

.overview {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 25px;
  margin-bottom: 30px;
  padding: 10px;
}

.overview-description {
  background-color: #f8f9fa;
  border-radius: 12px;
  padding: 25px;
  margin-top: 30px;
  border-left: 4px solid var(--primary);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.03);
}

.overview-description p {
  color: var(--gray);
  line-height: 1.7;
  margin: 0;
  text-align: justify;
  font-size: 1.05rem;
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