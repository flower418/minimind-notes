<template>
  <section class="sponsorship-section">
    <div class="sponsorship-container">
      <div class="sponsorship-header">
        <div class="header-badge">{{ copy.badge }}</div>
        <h2>{{ copy.title }}</h2>
        <p>{{ copy.description }}</p>
      </div>

      <div class="sponsorship-cards">
        <div
          v-for="method in methods"
          :key="method.name"
          class="sponsorship-card"
        >
          <div class="sponsorship-card-icon">
            <span class="method-emoji">{{ method.emoji }}</span>
            <span class="method-name">{{ method.name }}</span>
          </div>
          <img
            class="sponsorship-card-img"
            :src="method.image"
            :alt="method.name"
            loading="lazy"
          />
        </div>
      </div>

      <p class="sponsorship-note">{{ copy.note }}</p>
    </div>
  </section>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import { useLocale } from '../i18n'

const { isEn } = useLocale()

const copy = computed(() =>
  isEn.value
    ? {
        badge: '☕ Support',
        title: 'Buy me a coffee',
        description:
          'If this tutorial helped you understand LLM training, consider supporting future content. Hover the cards to reveal the QR codes.',
        note: 'Thank you for your support — it keeps the experiments coming!'
      }
    : {
        badge: '☕ 支持作者',
        title: '请作者喝杯咖啡',
        description:
          '如果这个教程帮助你理解了 LLM 训练，欢迎打赏支持后续内容更新。鼠标悬停卡片即可显示二维码。',
        note: '感谢你的支持 — 让对比实验持续做下去！'
      }
)

const methods = computed(() => [
  {
    name: isEn.value ? 'WeChat Pay' : '微信支付',
    emoji: '💚',
    image: '/wechat-qrcode.jpg'
  },
  {
    name: isEn.value ? 'Alipay' : '支付宝',
    emoji: '💙',
    image: '/alipay-qrcode.jpg'
  }
])
</script>

<style scoped>
.sponsorship-section {
  padding: 4rem 0 3rem;
  position: relative;
}

.sponsorship-container {
  max-width: 960px;
  margin: 0 auto;
  padding: 0 1.5rem;
}

.sponsorship-header {
  text-align: center;
  margin-bottom: 2.5rem;
}

.header-badge {
  display: inline-block;
  padding: 0.35rem 0.9rem;
  background: var(--vp-c-brand-soft);
  color: var(--vp-c-brand-1);
  border-radius: 999px;
  font-size: 0.85rem;
  font-weight: 600;
  margin-bottom: 1rem;
}

.sponsorship-header h2 {
  font-size: 2rem;
  font-weight: 700;
  margin: 0 0 0.75rem;
  border-top: none;
  padding-top: 0;
  color: var(--vp-c-text-1);
}

.sponsorship-header p {
  color: var(--vp-c-text-2);
  font-size: 1rem;
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.6;
}

.sponsorship-cards {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 1.5rem;
  max-width: 640px;
  margin: 0 auto;
}

.sponsorship-card {
  position: relative;
  aspect-ratio: 1;
  border: 1px solid var(--vp-c-divider);
  border-radius: 16px;
  overflow: hidden;
  background: var(--vp-c-bg-soft);
  transition: border-color 0.3s ease, transform 0.3s ease;
}

.sponsorship-card:hover {
  border-color: var(--vp-c-brand-1);
  transform: translateY(-2px);
}

.sponsorship-card-icon {
  position: absolute;
  inset: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 0.75rem;
  transition: opacity 0.3s ease;
  z-index: 2;
  pointer-events: none;
}

.method-emoji {
  font-size: 3rem;
  line-height: 1;
}

.method-name {
  font-size: 1rem;
  font-weight: 600;
  color: var(--vp-c-text-1);
}

.sponsorship-card-img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
  opacity: 0.25;
  filter: blur(8px);
  transition: opacity 0.3s ease, filter 0.3s ease;
}

.sponsorship-card:hover .sponsorship-card-icon {
  opacity: 0;
}

.sponsorship-card:hover .sponsorship-card-img {
  opacity: 1;
  filter: blur(0);
}

.sponsorship-note {
  text-align: center;
  margin-top: 2rem;
  color: var(--vp-c-text-2);
  font-size: 0.95rem;
}

@media (max-width: 540px) {
  .sponsorship-cards {
    grid-template-columns: 1fr;
    max-width: 320px;
  }

  .sponsorship-header h2 {
    font-size: 1.5rem;
  }
}
</style>
