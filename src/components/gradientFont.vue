<template>
  <div>
    <span class="font-gradient">用CSS实现文字渐变</span>
  </div>
</template>
<style lang="scss" scoped>
.font-gradient {
  background: linear-gradient(to right, red, #1a80ea);
  -webkit-background-clip: text;
  color: transparent;
}
</style>