<template>
  <div id="digital-flop">
    <dv-charts :option="rightOption" />
  </div>
</template>
<script>
const labelData = ['17:00', '16:00', '15:00', '14:00', '13:00', '12:00', '11:00', '10:00', '9:00'];
export default {
  name: "DigitalFlop",
  data() {
    return {
      
      rightOption: {
        backgroundColor: "#fff",
        legend: {
          data: ["游客流出", "游客流入"]
        },
        tooltip: {
          trigger: "axis",
          axisPointer: {
            type: "shadow"
          },
          formatter: function(a) {
            var v = a[0];
            return (
              v.name +
              "<br/>" +
              v.marker +
              v.seriesName +
              "：" +
              Math.abs(v.value)
            );
          }
        },
        xAxis: [
          {
            data: "value",
            min: -100,
            max: 0,
            gridIndex: 0,
            axisTick: {
              show: false
            },
            axisLabel: {
              show: true,
              formatter: function(v) {
                return v * -1;
              }
            },
            axisLine: {
              show: false
            },
            splitLine: {
              show: false
            }
          },
          {
            data: "value",
            gridIndex: 1,
            min: 0,
            max: 100,
            axisTick: {
              show: false
            },
            axisLine: {
              show: false
            },
            axisLabel: {
              show: true
            },
            splitLine: {
              show: false
            }
          }
        ],
        yAxis: [
          {
            data: "category",
            gridIndex: 0,
            inverse: true,
            data: labelData,
            axisTick: {
              show: false
            },
            axisLabel: {
              show: false
            },
            axisLine: {
              show: false
            }
          },
          {
            data: "category",
            gridIndex: 1,
            inverse: true,
            data: labelData,
            axisTick: {
              show: false
            },
            axisLabel: {},
            axisLine: {
              show: false //是否显示轴线
            }
          }
        ],
        grid: [
          {
            top: 50,
            width: "42%",
            left: 35,
            gridIndex: 0
          },
          {
            top: 50,
            left: "52%",
            right: 35,
            gridIndex: 1
          }
        ],
        color: ["#2FACFA", "#F5A623"],
        series: [
          {
            name: "游客流出",
            type: "bar",
            barWidth: 15,
            gridIndex: 0,
            itemStyle: {
              normal: {
                show: true,
                color: "#5de3e1",
                barBorderRadius: 50,
                borderWidth: 0,
                borderColor: "#333",
                label: {
                  show: true,
                  position: "left",
                  formatter: function(v) {
                    return v.value * -1;
                  }
                }
              }
            },
            data: [-50, -28, -40, -45, -38, -45, -56, -56, -12]
          },
          {
            name: "游客流入",
            type: "bar",
            barWidth: 15,
            xAxisIndex: 1,
            yAxisIndex: 1,
            itemStyle: {
              normal: {
                show: true,
                color: "#8A3EEB",
                barBorderRadius: 50,
                borderWidth: 0,
                borderColor: "#333",
                label: {
                  show: true,
                  position: "right",
                  formatter: function(v) {
                    return v.value;
                  }
                }
              }
            },
            data: [50, 28, 80, 65, 68, 45, 34, 23, 78]
          }
        ]
      }
    };
  },
  methods: {
    createData() {}
  },
  mounted() {
    const { createData } = this
    createData()
  }
};
</script>
<style scoped lang="less">
.dv-charts {
  height: calc(~"100% - 300px");
}
#digital-flop {
  width: 100%;
  height: 100%;
  color: #ffffff;
}
.lefttitle {
  font-size: 26px;

  margin: 10px 280px;
}
.tips {
  padding-left: 40px;
  display: flex;
  color: black;
  font-size: 20px;
  flex-direction: column;
  margin-left: 20px;
}
.dw {
  margin-left: 220px;
}
.chart-name {
  /* right: 70px; */
  text-align: right;
  font-size: 20px;
  top: 10px;
  color: black;
}
</style>
