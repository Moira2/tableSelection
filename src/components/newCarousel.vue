<template>
  <div>
    <div class="new-carousel">
      <el-carousel
        type="card"
        :autoplay="false"
        :loop="false"
        height="200px"
        @change="handleChange"
      >
        <!-- 左右显示箭头 -->
        <button
          v-if="isTop"
          class="el-carousel__arrow el-carousel__arrow--left hover-display"
        >
          <i class="el-icon-arrow-left"></i>
        </button>
        <button
          v-if="isBottom"
          class="el-carousel__arrow el-carousel__arrow--right hover-display"
        >
          <i class="el-icon-arrow-right"></i>
        </button>
        <el-carousel-item v-for="item in 6" :key="item">
          <div class="item-div">
            <h3>{{ item }}</h3>
          </div>
        </el-carousel-item>
      </el-carousel>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isTop: false,
      isBottom: false,
    };
  },
  mounted() {
    this.handleChange(0);
  },
  methods: {
    handleChange(e) {
      console.log("moira", e);

      setTimeout(() => {
        let doms = Array.from(document.getElementsByClassName("is-in-stage"));
        this.isTop = e === 0;
        this.isBottom = e === 5;
        for (let i = 0; i < doms.length; i++) {
          if (doms[i].className.includes("is-active")) {
            doms.splice(i, 1);
            for (let j = 0; j < doms.length; j++) {
              let style = doms[j].style.transform
                .match(/\((.+?)\)/g)[0]
                .replace("(", "")
                .replace("px)", "");
              doms[j].style.transform = `translateX(${
                +style > 0 ? +style + 120 : +style - 120
              }px) scale(0.83)`;
            }
          }
        }
      });
    },
  },
};
</script>
<style lang="scss">
</style>
<style scoped lang="scss">
.new-carousel {
  width: 500px;
  margin: 0 auto;
  //  左右显示箭头 
  .hover-display {
    opacity: 0;
  }
  .el-carousel__container:hover .hover-display{
    opacity: 1;
  }
  .el-carousel__item h3 {
    color: #475669;
    font-size: 14px;
    opacity: 0.75;
    line-height: 200px;
    margin: 0;
  }
  // .el-carousel__item:nth-child(2n) {
  //   background-color: #99a9bf;
  // }

  // .el-carousel__item:nth-child(2n+1) {
  //   background-color: #d3dce6;
  // }
  .el-carousel__item:nth-of-type(1) {
    background-color: pink;
  }
  .el-carousel__item:nth-of-type(2) {
    background-color: palevioletred;
  }
  .el-carousel__item:nth-of-type(3) {
    background-color: rgb(209, 216, 112);
  }
  .el-carousel__item:nth-of-type(4) {
    background-color: rgb(77, 50, 233);
  }
  .el-carousel__item:nth-of-type(5) {
    background-color: rgb(241, 61, 30);
  }
  .el-carousel__item:nth-of-type(6) {
    background-color: rgb(19, 16, 17);
  }
  //  .el-carousel__item:nth-child(2n) {
  //     background-color: #99a9bf;
  //   }

  //   .el-carousel__item:nth-child(2n+1) {
  //     background-color: #d3dce6;
  //   }

  .el-carousel__item {
    background: #ffffff;
    border: 3px solid #ffcc99;
    box-shadow: 0 8px 16px 0 #e91b16;
    border-radius: 12px;
  }
  .item-div {
    height: 200px;
    width: 200px;
  }
}
</style>