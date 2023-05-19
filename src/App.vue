<script setup lang="ts">
import { NConfigProvider, NNotificationProvider, NH1, darkTheme, useOsTheme } from 'naive-ui'
import { MyLayout, MyHeader, MyFooter } from '@libreservice/my-widget'
import MyPwa from './components/MyPwa.vue'
import { homepage, repopage } from '../package.json'

const osThemeRef = useOsTheme()
</script>

<template>
  <my-pwa />
  <!-- <my-font /> -->
  <n-config-provider :theme="osThemeRef === 'dark' ? darkTheme : null">
    <!-- <my-layout> -->
      <!-- <template #header>
        <my-header
          icon="./LibreService.svg"
          :homepage="homepage"
        />
      </template> -->
      <!-- <template #content> -->
        <div style="cursor: pointer; text-align: center; margin-top: 16px" onclick="window.location='https://github.com/alephpi/JumpType'" >
          <n-h1>JumpType 在线体验</n-h1>
          <div>Based on <a href="https://github.com/LibreService/my_rime">LibreService/my_rime</a></div>
        </div>
        <n-notification-provider :max="1">
          <router-view v-slot="{ Component }">
            <keep-alive>
              <component :is="Component" />
            </keep-alive>
          </router-view>
        </n-notification-provider>
      <!-- </template> -->
      <!-- <template #footer> -->
        <!-- <my-footer
          class="my-footer"
          :homepage="repopage"
          commit="__COMMIT__"
          build-date="__BUILD_DATE__"
          copyright="2022-2023 润心/alephpi"
        /> -->
      <!-- </template> -->
      
    <!-- </my-layout> -->
      <p style="padding: 20px;">
          <b>注释</b><br>
          1. 编码规则参见<a href='https://github.com/alephpi/JumpType/blob/master/readme.md#encoding-rules'>这里</a><br>
          2. 词库基本覆盖所有常见词，缺词请提<a href='https://github.com/alephpi/JumpType/issues'>issue</a><br>
          3. 本页面纯静态，网页加载时方案词典将一并加载到本地执行，不收集任何数据。<br>
        </p>
  </n-config-provider>
</template>
