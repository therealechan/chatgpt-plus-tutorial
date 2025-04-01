<template>
  <div class="steps-container">
    <StepItem 
      v-for="(step, index) in steps" 
      :key="index"
      :number="index + 1"
      :title="step.title"
      :substeps="step.substeps"
      :tips="step.tips"
    />
  </div>
</template>

<script>
import StepItem from './StepItem.vue'

export default {
  name: 'StepsSection',
  components: {
    StepItem
  },
  data() {
    return {
      steps: [
        {
          title: '准备美国区 Apple ID',
          substeps: [
            {
              title: '方法一：从中国区转换为美国区',
              description: '先注册中国区 Apple ID，无需使用 VPN。在 App Store 购买一个免费应用后，前往 Apple ID 账户页面（appleid.apple.com）登录并将地区更改为美国。请注意，更改地区前需要确保中国区账户内没有余额，并且取消所有订阅服务。',
              hasImage: false
            },
            {
              title: '方法二：直接购买现成的美区 Apple ID',
              description: '如果你不想自己转换区域，可以前往 mtcer.com 等专业平台直接购买一个现成的美区 Apple ID。这种方式更为便捷，但请选择信誉良好的平台以确保账户安全和有效性。',
              hasImage: false
            },
            {
              title: '验证账户',
              description: '无论选择哪种方法获取美区 Apple ID，都需要确保账户能够正常登录和使用。',
              hasImage: false
            },
            {
              title: '登录 App Store',
              description: '在你的 iOS 设备上，使用美国区 Apple ID 登录 App Store。',
              hasImage: true
            }
          ],
          tips: '使用美国区 Apple ID 时，可以不需要提供美国信用卡，只需选择"None"作为付款方式。后续我们会使用 Gift Card 充值。如果使用方法一转区，转区后可能需要提供美国地址信息，可使用美国酒店或商业地址。购买现成账号时，注意修改密码和安全问题，增强账户安全性。'
        },
        {
          title: '设置美国线路 VPN',
          substeps: [
            {
              title: '选择可靠的 VPN 服务',
              description: '选择一个提供美国服务器的可靠 VPN 服务，如 NordVPN、ExpressVPN 等。',
              hasImage: false
            },
            {
              title: '安装 VPN 应用',
              description: '在你的设备上下载并安装所选 VPN 的应用程序。',
              hasImage: false
            },
            {
              title: '连接到美国服务器',
              description: '打开 VPN 应用，选择并连接到美国的服务器。确保连接成功，你的 IP 地址已更改为美国地址。',
              hasImage: false
            }
          ],
          tips: '选择速度较快的服务器，这将有助于提高后续操作的流畅度。在整个过程中保持 VPN 连接，以避免地理位置限制问题。'
        },
        {
          title: '下载 ChatGPT 应用',
          substeps: [
            {
              title: '确保 VPN 已连接',
              description: '确认你的 VPN 已连接到美国服务器。',
              hasImage: false
            },
            {
              title: '切换到美区 Apple ID',
              description: '在 iOS 设备上切换到美区 Apple ID 的步骤如下：<ol style="margin-left: 20px; margin-top: 10px;"><li>打开"设置"应用</li><li>点击顶部的你的姓名/Apple ID</li><li>点击"媒体与购买项目"</li><li>选择"退出登录"</li><li>返回到设置主页，再次点击顶部（现在显示"登录到您的iPhone"）</li><li>选择"使用现有的Apple ID登录"</li><li>输入你的美区Apple ID和密码</li><li>完成验证步骤</li></ol>',
              hasImage: true
            },
            {
              title: '打开 App Store',
              description: '使用你的美国区 Apple ID 登录 App Store。',
              hasImage: true
            },
            {
              title: '搜索并下载 ChatGPT',
              description: '在搜索栏中输入"ChatGPT"，找到官方应用并点击下载。',
              hasImage: true
            }
          ],
          tips: '确保下载的是 OpenAI 官方的 ChatGPT 应用，避免下载第三方应用以保护账户安全。'
        },
        {
          title: '购买和充值 Apple Gift Card',
          substeps: [
            {
              title: '在可信平台购买 Gift Card',
              description: '在海鲜市场或其他可信的在线平台购买美元面值的 Apple Gift Card。ChatGPT Plus 每月订阅费用为 $19.99，建议购买至少 $20 的礼品卡。',
              hasImage: false
            },
            {
              title: '获取礼品卡代码',
              description: '完成购买后，你将收到礼品卡的兑换代码。保存好这个代码。代码示例：<span class="code-example">XVLM572LNXF3T9FA</span>',
              hasImage: false
            },
            {
              title: '兑换礼品卡',
              description: '打开 App Store，点击右上角的个人头像，选择"兑换礼品卡或代码"，然后输入你的礼品卡代码进行兑换。<br><br>示例代码：<div class="code-block"><span class="code-example">XVLM572LNXF3T9FA</span></div>',
              hasImage: true
            },
            {
              title: '确认余额',
              description: '兑换成功后，检查你的 Apple ID 账户余额，确保金额已经到账。',
              hasImage: false
            }
          ],
          tips: '购买 Gift Card 时，选择可信的卖家以避免购买到无效的礼品卡。如果是首次充值美国区 Apple ID，系统可能会要求你提供一个美国地址，可以使用美国酒店或商业地址。'
        },
        {
          title: '开通 ChatGPT Plus',
          substeps: [
            {
              title: '确保 VPN 已连接',
              description: '再次确认你的 VPN 已连接到美国服务器。',
              hasImage: false
            },
            {
              title: '打开 ChatGPT 应用',
              description: '打开已下载的 ChatGPT 应用，如果还没有 OpenAI 账户，按照提示创建一个。',
              hasImage: false
            },
            {
              title: '使用 Google 账号登录',
              description: '除了直接使用电子邮件注册 OpenAI 账户外，你也可以选择使用 Google 账号授权登录 ChatGPT，这样可以省去单独创建和记忆 OpenAI 账户密码的步骤。在登录页面上，点击"Continue with Google"选项，然后按照提示完成 Google 账号授权即可。',
              hasImage: true
            },
            {
              title: '找到订阅选项',
              description: '在应用中，点击左上角的个人头像或设置图标，找到"升级到 Plus"或类似的选项。',
              hasImage: true
            },
            {
              title: '完成订阅',
              description: '选择 ChatGPT Plus 订阅，确认月费为 $19.99，然后使用你的 Apple ID 余额完成支付。',
              hasImage: true
            },
            {
              title: '验证订阅状态',
              description: '支付成功后，你的账户将立即升级为 ChatGPT Plus。你可以在设置中查看你的订阅状态。',
              hasImage: false
            }
          ],
          tips: '订阅成功后，你将获得 ChatGPT Plus 的所有高级功能，包括优先访问、更快的响应速度以及对最新模型的访问权限。订阅会自动续费，如果不需要继续使用，记得在下个计费周期前取消订阅。'
        }
      ]
    }
  }
}
</script>

<style scoped>
.steps-container {
  margin-bottom: 40px;
}
</style> 