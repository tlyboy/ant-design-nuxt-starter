<script setup lang="ts">
import { appName } from './constants'
import { theme } from 'ant-design-vue'
import zhCN from 'ant-design-vue/es/locale/zh_CN'

const color = useColorMode()

const locale = ref(zhCN)

useHead({
  htmlAttrs: {
    lang: 'zh-CN',
  },
  title: appName,
})
</script>

<template>
  <a-config-provider
    :theme="{
      token: {
        colorPrimary: '#3498db',
      },
      algorithm:
        color.value === 'dark' ? theme.darkAlgorithm : theme.defaultAlgorithm,
    }"
    :locale="locale"
  >
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </a-config-provider>
</template>
