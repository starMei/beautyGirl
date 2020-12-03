<template>
  <div id="digital-flop">
    <div class="topMiddle">
      <div class="topmiddletitle">
        <span>预计港口装柜条</span>
      </div>
      <div class="tip">
        <div><span>旧产品合计:</span><span class="tip1">{{ newPro }}</span></div>
        <div><span>新产品合计:</span><span class="tip1">{{ oldPro }}</span></div>
        <div><span>总量:</span><span class="tip1">{{ Total }}</span></div>
      </div>
    </div>
    <dv-charts :option="option"/>
  </div>
</template>
<script>
export default {
  name: "DigitalFlop",
  data() {
    return {
      newPro: 123,
      oldPro: 123,
      Total: 246,
      option: {
        legend: {
          data: [
            {
              name: "新产品",
              color: "#00baff"
            },
            {
              name: "旧产品",
              color: "blue"
            }
          ],
          textStyle: {
            fill: "#fff"
          }
        },
        toolbox: {
          show: true,
          feature: {
            dataView: { show: true, readOnly: false },
            magicType: { show: true, type: ["line", "bar"] },
            restore: { show: true },
            saveAsImage: { show: true }
          }
        },
        xAxis: {
          data: [
            "乍浦",
            "青岛",
            "宁波",
            "福州",
            "南京",
            "厦门",
            "盐田",
            "天津",
            "九江",
            "独山",
            "江阴",
            "重庆",
            "连云港",
            "中山",
            "洋山",
            "张家港"
          ],
          axisLine: {
            lineStyle: {
              color: "#fff",
              width: 2
            }
          },
          axisLabel: {
            style: {
              fill: "#fff",
              fontSize: "12px"
            }
          }
        },
        yAxis: {
          data: "value",
          axisLine: {
            lineStyle: {
              color: "#fff",
              width: 2,
              fontSize: "12px"
            }
          },
          axisLabel: {
            style: {
              fill: "#fff"
            }
          }
        },
        series: [
          {
            name: "新产品",
            color: "#00baff",
            data: [
              1200,
              2230,
              1900,
              2100,
              3500,
              4200,
              3985,
              1200,
              2230,
              1900,
              2100,
              3500,
              4200,
              3985,
              1200,
              2230,
              1900
            ],
            type: "bar"
          },
          {
            name: "旧产品",
            data: [
              1200,
              2230,
              1900,
              2100,
              3500,
              4200,
              3985,
              1200,
              2230,
              1900,
              2100,
              3500,
              4200,
              3985,
              1200,
              2230,
              1900
            ],
            type: "bar",
            color: "blue"
          }
        ]
      }
    };
  },
  methods: {
    createData() {}
  },
  mounted() {
    const { createData } = this;
    createData();
  }
};
</script>
<style scoped lang="less">
#digital-flop {
  width: 100%;
  height: 100%;
  color: #ffffff;
}
.dv-charts{
  height: calc(~"100% - 30px");
}
.topMiddle {
  height: 35px;
}
.topmiddletitle {
  text-align: center;
  font-size: 18px;
  color: "#fff";
}
.tip {
  display: flex;
  margin-left: 120px;
  flex-direction: column;
}
.tip1{
  margin-left: 150px;
}
.chart-name {
  text-align: right;
  font-size: 20px;
  top: 10px;
  color: black;
}
</style>
