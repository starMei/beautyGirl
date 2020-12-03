<template>
  <div id="data-view">
    <dv-full-screen-container>
      <top-header />
      <dv-border-box-1 class="main-container">
        <div class="main-container">
          <!-- 顶部显示 -->
          <div class="top">
            <div style="width:20%">
              <digital-flop />
            </div>
            <div style="width:60%">
              <top-middle />
            </div>
            <div style="width:20%">
              <digital-flop />
            </div>
          </div>
          <!-- 中间数据显示 -->

          <div class="middle">
            <div style="width:40%">
              <dv-border-box-13>
                <middle-left />
              </dv-border-box-13>
            </div>
            <div style="width:60%">
              <dv-border-box-13>
                <middle-right />
              </dv-border-box-13>
            </div>
          </div>

          <!-- 底部图形 -->

          <div class="bottom">
            <div style="width:40%">
              <dv-border-box-8>
                <bottom-left />
              </dv-border-box-8>
            </div>
            <div style="width:60%">
              <dv-border-box-8>
                <bottom-right />
              </dv-border-box-8>
            </div>
          </div>
        </div>
      </dv-border-box-1>
    </dv-full-screen-container>
  </div>
</template>

<script>
import TopHeader from "./TopHeader";
import DigitalFlop from "./DigitalFlop";
import TopMiddle from "./TopMiddle";
import MiddleLeft from "./MiddleLeft";
import MiddleRight from "./MiddleRight";
import BottomLeft from "./BottomLeft";
import BottomRight from "./BottomRight";
export default {
  name: "bidata",
  components: {
    TopHeader,
    DigitalFlop,
    TopMiddle,
    MiddleLeft,
    MiddleRight,
    BottomLeft,
    BottomRight
  },
  data() {
    return {
      MiddleRightreturn:{}
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
#data-view {
  width: 100%;
  height: 100%;
  background-color: #030409;
  color: #fff;
  .main-container {
    height: calc(~"100% - 130px");
    .top {
      display: flex;
      height: 33%;
    }
    .middle {
      height: 33%;
    }
    .middle,
    .bottom {
      box-sizing: border-box;
      height: 34%;
      margin-top: 40px;
      display: flex;
    }
  }
}
#dv-full-screen-container {
  background-image: url("../assets/bg.png");
  background-size: 100% 100%;
  box-shadow: 0 0 3px blue;
  display: flex;
  color: #ffffff;
  flex-direction: column;
}
</style>
