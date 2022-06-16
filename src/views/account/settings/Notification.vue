<template>
  <a-card>
    <a-list itemLayout="horizontal" :dataSource="data"> </a-list>
    <div style="height: 400px" id="main"></div>
  </a-card>
</template>

<script>
import * as echarts from 'echarts'
export default {
  data () {
    return {
      data: []
    }
  },

  mounted () {
    this.initChart()
  },

  methods: {
    initChart () {
      // 基于准备好的dom，初始化echarts实例
      var myChart = echarts.init(document.getElementById('main'))
      // 绘制图表
      myChart.setOption({
        title: {
          text: 'ECharts 入门示例'
        },
        legend: {
          data: [
            '产值',
            'GDP',
            '收入'
          ]
        },
        tooltip: {},
        xAxis: {
          data: [
            '平均亩产值(万元/亩)',
            '单位厂房面积产值GDP(万元)',
            '单位厂房面积产值GDP(万元)2',
            '单位厂房面积产值GDP(万元)3',
            '单位厂房面积产值GDP(万元)4',
            '单位厂房面积产值GDP(万元)5',
            '单位厂房面积产值GDP(万元)6',
            '单位厂房面积产值GDP(万元)7',
            '单位厂房面积产值GDP(万元)8',
            '单位厂房面积产值GDP(万元)9',
            '单位厂房面积产值GDP(万元)10'
          ],
          axisLabel: {
            interval: 0,
            width: 10,
            rotate: -15
            // lineHeight: 100,
            // overflow: 'truncate',
            // // 使用字符串模板，模板变量为刻度默认标签 {value}
            // formatter: '{value} kg',
            // showMaxLabel: true,
            // // lineHeight: 80,
            // ellipsis: '...'
          }
        },
        yAxis: {},
        series: [
          {
            name: '产值',
            type: 'bar',
            data: [5, 20, 36, 10, 10, 20, 34, 23, 12, 22, 90]
          },
           {
            name: 'GDP',
            type: 'bar',
            data: [25, 220, 236, 210, 210, 220, 324, 223, 212, 222, 290]
          },
           {
            name: '收入',
            type: 'bar',
            data: [35, 320, 336, 310, 310, 320, 334, 323, 312, 322, 390]
          }
        ]
      })
    }
  }
}
</script>

<style scoped>
</style>
