<template>
    <div id="digital-flop">
     <div class="topLeft">
      <div class="topLefttitle">
        <span>下单未出货数量与金额</span>
      </div>
      <div class="tip">
        <div><span>下单总金额:{{ TotalMoney }}</span><span class="tip1">单位：人民币</span></div>
        <div><span>下单总数量:{{ TotalCount }}</span><span class="tip1"></span></div>
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
    TotalMoney:1234.32,
    TotalCount:32343,
     option: {
        legend: {
          data: [
            {
              name: '下单金额',
              color: '#00baff'
            },
            {
              name: '下单数量',
              color: '#ff5ca9'
            }
          ],
          textStyle: {
            fill: '#fff'
          }
        },
        xAxis: {
          data: [
            '国际合作', '蔻特', '新鼎瑞利', '扬格', '美国公司'
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
          max: 8
        },
        series: [
          {
            name: '下单金额',
            data: [
              2.5, 3.5, 6.5, 6.5, 7.5
            ],
            type: 'bar',
             barWidth : 30,
            barStyle: {
              fill: 'rgba(0, 186, 255, 0.4)'
            }
          },
          {
            name: '下单数量',
            data: [
              3, 3.7, 4, 5, 8
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
  height: calc(~"100% - 30px");
}
.topLeft {
  height: 35px;
}
.topLefttitle {
  text-align: center;
  font-size: 18px;
  color: "#fff";
}
.tip {
  /* width: 200px;
  height: 100px; */
  display: flex;
  margin-left: 40px;
  flex-direction: column;
}
.tip1{
  margin-left: 90px;
}
</style>
