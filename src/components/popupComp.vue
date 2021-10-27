<template>
  <div>
    <el-button type="primary" @click="showCard = true">点击触发弹窗</el-button>
    <div class="mask-layer" @click="showCard = false" v-if="showCard"></div>
    <div
      class="bottom-card"
      :class="showCard ? 'bottom-card-in' : 'bottom-card-out'"
    >
      contentcontentcontentcontent
    </div>
  </div>
</template>
<script>
export default {
  name: "popupComp",
  data() {
    return {
      showCard: true,
    };
  },
  mounted() {},
};
</script>
<style scoped lang="scss">
@keyframes popup {
  from {
    height: 0;
  }
  to {
    height: 70vh;
  }
}
@keyframes popout {
  // from {
  //   // height: 50vh;
  //   transform: translateY(50%);
  //   opacity: 0.7;
  // }
  // to {
  //   transform: translateY(0);
  //   opacity: 0;
  // }
  from {
    height: 70vh;
  }
  to {
    height: 0vh;
    opacity: 0;
  }
}
.mask-layer {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: black;
  opacity: 0.7;
}

.bottom-card {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  height: calc(70vh);
  background: pink;
  &.bottom-card-in {
    animation: popup ease 1s;
  }
  &.bottom-card-out {
    animation: popout ease-out 1s;
    height: 0;
  }
}
</style>