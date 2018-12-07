# wepy-echarts
程序对https://github.com/ecomfe/echarts-for-weixin 进行封装 , 可以直接在wepy框架中使用
# 最完美的封装:
    <chart :option.sync="option"  canvasId="aaa" height="300px"></chart> 
# 使用方法
1, 下载本工程

2, npm install wepy-cli -g

3, cd wepy-echarts

4, npm  install

5, npm run dev 

6, 运行微信web开发者工具 导入本工程

# 如何单独使用组件
 1, 下载https://github.com/ecomfe/echarts-for-weixin  , 将 ec-canvas 和 pages 目录放入 native目录
 
 2, 下载本工程 components\echarts.wpy , 放入components目录
 
 3, 代码
    
        
 wxml模版
   
    <template lang="wxml">
      <view class="echart">
        <chart :option.sync="option"  canvasId="aaa" height="300px"></chart> 
        <chart1 :option.sync="option1" canvasId="bbb" height="300px"></chart1> 
        <chart2 :option.sync="option2" canvasId="ccc"  height="300px"></chart2> 
      </view>
    </template>
    
 page wpy文件中引入
    
    import chart from '../../components/echarts';
    ...
    config = {
      usingComponents: {
        'ec-canvas': '../../native/echarts/ec-canvas/ec-canvas'
      }
    };
    components = {
      chart: chart,
      chart1: chart,
      chart2: chart
    };
    data = {
      option: {
        title: {
          text: 'ECharts 示例'
        },
        tooltip: {},
        legend: {
          data: ['销量']
        },
        xAxis: {
          data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
        },
        yAxis: {},
        series: [
          {
            name: '销量',
            type: 'bar',
            data: [5, 20, 36, 10, 10, 20]
          }
        ]
      },
      option1: {
        title: {
          text: '某站点访问来源',
          subtext: '纯属虚构',
          x: 'center'
        },
        tooltip: {
          trigger: 'item',
          formatter: '{a} <br/>{b} : {c} ({d}%)'
        },
        legend: {
          orient: 'vertical',
          left: 'left',
          data: ['直接访问', '邮件营销', '联盟广告', '视频广告', '搜索引擎']
        },
        series: [
          {
            name: '访问来源',
            type: 'pie',
            radius: '55%',
            center: ['50%', '60%'],
            data: [
              { value: 335, name: '直接访问' },
              { value: 310, name: '邮件营销' },
              { value: 234, name: '联盟广告' },
              { value: 135, name: '视频广告' },
              { value: 1548, name: '搜索引擎' }
            ],
            itemStyle: {
              emphasis: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: 'rgba(0, 0, 0, 0.5)'
              }
            }
          }
        ]
      },
      option2:  {
        xAxis: {
          type: 'category',
          data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
        },
        yAxis: {
          type: 'value'
        },
        series: [
          {
            data: [820, 932, 901, 934, 1290, 1330, 1320],
            type: 'line'
          }
        ]
      }
    };

    
    
