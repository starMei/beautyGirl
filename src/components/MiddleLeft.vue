<template>
    <div id="digital-flop">
      <div class="topLeft">
      <div class="topLefttitle">
        <span>下单未出货中预计交货期距今天数</span>
      </div>
    </div>
      <dv-charts :option="option"/>
  </div>
</template>
<script>
export default {
  name: 'DigitalFlop',
  data () {
    return {
    digitalFlopData: [],
     option: {
        legend: {
          data: [
            {
              name: '总金额（RMB）',
              color: '#00baff'
            },
            {
              name: '总体积（m³）',
              color: '#ff5ca9'
            }
          ],
          textStyle: {
            fill: '#fff'
          }
        },
        xAxis: {
          data: [
            '<0', '0-29', '30-59', '60-89', '90-119','>120'
          ],
          axisLine: {
            style: {
              stroke: '#fff'
            }
          },
          axisLabel: {
            style: {
              fill: '#fff',
              fontSize:'12px'
            }
          },
          axisTick: {
            show: false
          }
        },
        yAxis: {
          data: 'value',
          splitLine: {
            show: false
          },
          axisLine: {
            style: {
              stroke: '#fff'
            }
          },
          axisLabel: {
            style: {
              fill: '#fff',
              fontSize:'12px'
            }
          },
          axisTick: {
            show: true
          },
          min: 0,
          max: 200
        },
        series: [
          {
            name: '总金额（RMB）',
            data: [
              12,22,33,44,65,123
            ],
            type: 'bar',
            barWidth : 30,
            barStyle: {
              fill: 'rgba(0, 186, 255, 0.4)'
            }
          },
          {
            name: '总体积（m³）',
            data: [
              14,26,37,48,69,129
            ],
            type: 'line',
            smooth:true,
            lineStyle: {
              stroke: '#ff5ca9'
            },
            linePoint: {
              radius: 4,
              style: {
                fill: '#ff5ca9',
                stroke: 'transparent'
              }
            }
          }
        ]
      }
    }
  },
  methods: {
    createData () {
      
    }
  },
  mounted () {
    const { createData } = this
    createData()
  }
}
</script>
<style scoped lang="less">
#digital-flop{
  width:100%;
  height: 100%;
}
.dv-charts{
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
