<template>
  <header role="banner">
    <div class="title-container">
      <img src="/assets/logo/OpenAI-white-monoblossom.svg" alt="ChatGPT Logo" class="logo" />
      <h1 itemprop="headline">ChatGPT Plus 订阅教程</h1>
    </div>
    <p class="subtitle" itemprop="alternativeHeadline">一步步指导你如何开通 ChatGPT Plus 会员服务</p>
  </header>
</template>

<script>
export default {
  name: 'AppHeader'
}
</script>

<style scoped>
header {
  text-align: center;
  padding: 40px 0;
  background: linear-gradient(135deg, var(--primary), var(--secondary));
  color: white;
  border-radius: 12px;
  margin-bottom: 30px;
  box-shadow: 0 4px 20px rgba(16, 163, 127, 0.2);
}

.title-container {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 15px;
}

.logo {
  width: 50px;
  height: 50px;
  margin-right: 15px;
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 0;
}

.subtitle {
  font-size: 1.2rem;
  opacity: 0.9;
  margin-bottom: 15px;
  padding: 0 15px;
}

@media (max-width: 768px) {
  header {
    padding: 30px 0;
    margin-bottom: 25px;
    border-radius: 10px;
  }
  
  .title-container {
    flex-direction: row;
    align-items: center;
  }
  
  h1 {
    font-size: 2rem;
  }
  
  .logo {
    width: 40px;
    height: 40px;
    margin-right: 10px;
  }
  
  .subtitle {
    font-size: 1.1rem;
    padding: 0 20px;
  }
}

@media (max-width: 480px) {
  header {
    padding: 25px 0;
    margin-bottom: 20px;
    border-radius: 8px;
  }
  
  .title-container {
    flex-direction: column;
    margin-bottom: 12px;
  }
  
  h1 {
    font-size: 1.8rem;
    text-align: center;
    margin-top: 8px;
  }
  
  .logo {
    margin-right: 0;
    margin-bottom: 5px;
  }
  
  .subtitle {
    font-size: 1rem;
    padding: 0 15px;
  }
}
</style> 