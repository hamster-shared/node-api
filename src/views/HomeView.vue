<template>
  <span class="text-blue-700">title</span>
  <Button type="primary" @click="changeLang">中/En</Button>
  <hr />
  <span class="text-6xl">{{ $t("home.test") }}</span>
  <hr />
  <Button type="dashed" size="small"> ant </Button>
  <div class="test-less">
    <span>11111</span>
    <span class="less-child">222222</span>
  </div>
  <WagmiConfig><ConnectButton label="Sign in" /></WagmiConfig>
</template>

<script setup lang="ts">
import { Button } from "ant-design-vue";
import WagmiConfig from '@/components/WagmiConfig.vue';
import { ConnectButton } from '@rainbow-me/rainbowkit';
const changeLang = () => {
  const language = window.localStorage.getItem("language");

  if (language == undefined || language == "zh") {
    window.localStorage.setItem("language", "en");
    location.reload();
  } else {
    window.localStorage.setItem("language", "zh");
    location.reload();
  }
};

const YourApp = () => {
  return '<ConnectButton />';
};
</script>

<style lang="less" scoped>
@baseColoe: orange;
.test-less {
  background: red;
  .less-child {
    background: @baseColoe;
  }
}
</style>
