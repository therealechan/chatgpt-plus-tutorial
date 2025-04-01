<template>
  <div class="faq">
    <h2>常见问题解答</h2>
    
    <div v-for="(item, index) in faqItems" :key="index" class="faq-item">
      <div class="faq-question">Q: {{ item.question }}</div>
      <div class="faq-answer">A: {{ item.answer }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FaqSection',
  data() {
    return {
      faqItems: [
        {
          question: '我需要一直使用 VPN 吗？',
          answer: '在完成订阅后，使用 ChatGPT 时通常仍需要连接 VPN。不过，一些地区在订阅后可能不需要 VPN 也能使用，但这取决于你所在的地区和网络环境。'
        },
        {
          question: '如果我的 Gift Card 充值失败怎么办？',
          answer: '确保你使用的是美国区 Apple ID，并且 Gift Card 是美元面值的。如果仍然失败，可以联系 Apple 支持或 Gift Card 的卖家寻求帮助。'
        },
        {
          question: 'ChatGPT Plus 的订阅是否会自动续费？',
          answer: '是的，ChatGPT Plus 是一个自动续费的订阅服务。如果你不想继续使用，需要在下一个计费周期开始前手动取消订阅。'
        },
        {
          question: '我可以在多个设备上使用同一个 ChatGPT Plus 账户吗？',
          answer: '是的，你可以在多个设备上使用同一个 ChatGPT 账户，只要你登录的是同一个 OpenAI 账户即可。'
        },
        {
          question: '如何取消 ChatGPT Plus 订阅？',
          answer: '要取消订阅，打开 iOS 设置，点击你的 Apple ID，然后选择"订阅"，找到 ChatGPT Plus 并选择"取消订阅"。'
        },
        {
          question: '我可以在不同的 Apple ID 之间快速切换吗？',
          answer: '是的，你可以在 App Store 中快速切换 Apple ID。打开 App Store，点击右上角的个人头像，滑动到底部，点击退出登录，然后输入另一个 Apple ID 的凭据即可。需要注意的是，只切换 App Store 的账号不会影响设备的 iCloud 账号。'
        }
      ]
    }
  }
}
</script>

<style scoped>
.faq {
  background: white;
  border-radius: 12px;
  padding: 30px;
  margin-bottom: 30px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
}

.faq h2 {
  margin-bottom: 20px;
  color: var(--primary);
  text-align: center;
}

.faq-item {
  margin-bottom: 20px;
  border-bottom: 1px solid var(--light-gray);
  padding-bottom: 20px;
}

.faq-question {
  font-weight: 600;
  margin-bottom: 10px;
}

.faq-answer {
  color: var(--gray);
}

/* Mobile responsiveness */
@media (max-width: 768px) {
  .faq {
    padding: 25px 20px;
    margin-bottom: 25px;
  }
  
  .faq h2 {
    font-size: 1.5rem;
    margin-bottom: 15px;
  }
  
  .faq-item {
    margin-bottom: 15px;
    padding-bottom: 15px;
  }
}

@media (max-width: 480px) {
  .faq {
    padding: 20px 15px;
    margin-bottom: 20px;
    border-radius: 10px;
  }
  
  .faq h2 {
    font-size: 1.3rem;
    margin-bottom: 12px;
  }
  
  .faq-item {
    margin-bottom: 12px;
    padding-bottom: 12px;
  }
  
  .faq-question {
    font-size: 0.95rem;
  }
  
  .faq-answer {
    font-size: 0.9rem;
  }
}
</style> 