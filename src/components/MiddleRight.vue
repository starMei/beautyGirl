<template>
  <div id="digital-flop">
    <div class="topLeft">
      <div class="topLefttitle">
        <span>实际装柜日期距合同预计交货期天数</span>
      </div>
    </div>
    <dv-charts :option="option" />
  </div>
</template>
<script>
export default {
  name: "DigitalFlop",
  //
  data() {
    return {
      digitalFlopData: [],
      option: {
        legend: {
          data: ["各个区间天数的装柜体积占比"],
          textStyle: {
            fill: "#fff"
          }
        },
        xAxis: {
          data: [
            "提交",
            "准时",
            "延迟1-15",
            "延迟16-30",
            "延迟31-45",
            "延迟46-60",
            "延迟>61"
          ],
          axisLine: {
            style: {
              stroke: "#fff"
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
            style: {
              stroke: "#fff"
            }
          },
          axisLabel: {
            style: {
              fill: "#fff",
              fontSize: "12px"
            }
          }
        },
        series: [
          {
            name: "各个区间天数的装柜体积占比",
            data: [1200, 2230, 1900, 2100, 3500, 4200, 3985],
            type: "bar",
            barWidth: 30
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
}
.dv-charts {
  height: calc(~"100% - 200px");
}
.topLeft {
  height: 35px;
}
.topLefttitle {
  margin-top:20px;
  text-align: center;
  font-size: 18px;
  color: "#fff";
}
</style>
