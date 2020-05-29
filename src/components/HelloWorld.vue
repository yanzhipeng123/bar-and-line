<template>
  <div class="hello">
    <div class="box" ref="myCharts">
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App"
    };
  },
  mounted() {
    const my = this.$echarts.init(this.$refs.myCharts);
    let options = {
        title:{
          text:"我是主标题",
          subtext:"我是副标题"
        },
        tooltip:{
          trigger:"axis"
        },
        legend:{
          data:["男","女"]
        },
        toolbox:{
          show:true,
          feature:{
            mark:{
              show:true
            },
            dataView:{
              show:true,
              readOnly:false
            },
            magicType:{
              show:true,
              type:["line","bar"]
            }
          }
        },
        calculable:true,
        xAxis:[
          {
            type:"category",
            data:["1月","二月","三月","四月","五月","六月"]
          }
        ],
        yAxis:[{}],
        series:[
          {
            name:"男",
            type:"bar",
            data:[15,17,20,4,9,88]
          },
           {
            name:"女",
            type:"bar",
            data:[0,27,6,4,9,98]
          }
        ]
    };
    my.setOption(options);
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.box {
  width: 600px;
  height: 400px;
}
</style>
