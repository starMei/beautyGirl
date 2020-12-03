<template>
  <div id="digital-flop">
    <div class="topMiddle">
      <div class="topmiddletitle">
        <span>月平均交货与海运时长</span>
      </div>
      <div class="tip">
        <div>
          <span>累计交货时长:</span><span class="tip1">{{ deliveryTime }}</span>
        </div>
        <div>
          <span>累计海运时长:</span><span class="tip1">{{ seaTime }}</span>
        </div>
      </div>
    </div>
    <dv-charts :option="option" />
  </div>
</template>
<script>
export default {
  name: "DigitalFlop",
  data() {
    return {
      deliveryTime: 1234,
      seaTime: 1234,
      option: {
        legend: {
          data: [
            {
              name: "交货时长",
              color: "#00baff"
            },
            {
              name: "海运时长",
              color: "blue"
            },
            {
              name: "采购合同时效履行率",
              color: "#CC6600"
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
            "1月",
            "2月",
            "3月",
            "4月",
            "5月",
            "6月",
            "7月",
            "8月",
            "9月",
            "10月",
            "11月",
            "12月",
            "1月",
            "2月",
            "3月",
            "4月",
            "5月",
            "6月",
            "7月",
            "8月",
            "9月",
            "10月",
            "11月"
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
            name: "交货时长",
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
              1900,
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
              2230
            ],
            type: "bar"
          },
          {
            name: "海运时长",
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
              1900,
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
          },
          {
            name: "采购合同时效履行率",
            data: [
              1200,
              2300,
              1223,
              1200,
              2300,
              1223,
              1200,
              2300,
              1223,
              1200,
              2300,
              1200,
              2300,
              1223,
              1200,
              2300,
              1223,
              1200,
              2300,
              1223,
              1200,
              2300,
              2300
            ],
            type: "line",
            smooth: true,
            lineStyle: {
              stroke: "#CC6600"
            },
            linePoint: {
              radius: 4,
              style: {
                fill: "#CC6600",
                stroke: "transparent"
              }
            }
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
.dv-charts {
    height: calc(~"100% - 300px");
  }
.topMiddle {
  height: 35px;
}
.topmiddletitle {
  text-align: center;
  font-size: 18px;
  color: "#fff";
  margin-top:40px;
}
.tip {
  display: flex;
  margin-left: 30px;
  flex-direction: column;
}
.tip1 {
  margin-left: 80px;
}
</style>
