# wepy-echarts
程序对https://github.com/ecomfe/echarts-for-weixin 进行封装 , 可以直接在wepy框架中使用
# 使用方法
1, 下载本工程

2, 参考wepy的安装

3, 运行微信web开发者工具 导入本工程
# 如何单独使用组件
 1, 下载https://github.com/ecomfe/echarts-for-weixin  , 将 ec-canvas 和 pages 目录放入 native\
 2, 下载本工程 components\echarts.wpy , 放入components\
 3, 在page中引入

    import chart from '../../components/echarts';
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
    
    模版
    <template lang="wxml">
      <view class="echart">
        <chart :option.sync="option"  height="300px"></chart> 
        <chart1 :option.sync="option1"  height="300px"></chart1> 
        <chart2 :option.sync="option2"  height="300px"></chart2> 
      </view>
    </template>
    
    
