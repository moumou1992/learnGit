<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    当前时间：{{ currentTime }}
  </div>
</template>

<script>
import moment from 'moment';
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return{
      currentTime:''
    }
  },
  mounted(){
    this.init();
  },
  methods:{
    init(){
      this.currentTime = moment().format("YYYY-MM-DD HH:mm:ss");//当前时间
      console.log(moment().subtract(10, "days").format("YYYY-MM-DD HH:mm:ss"));//当前时间的前10天时间
      console.log(moment().subtract(1, "years").format("YYYY-MM-DD"));//当前时间的前1年时间
      console.log(moment().subtract(3, "months").format("YYYY-MM-DD")); //当前时间的前3个月时间
      console.log(moment().subtract(1, "weeks").format("YYYY-MM-DD"));//当前时间的前一个星期时间
      console.log(moment().add(-6, 'hours').format('YYYY-MM-DD HH:mm:ss'));//当前日期的（负数）前多少（小时、天、周、月、年）
      console.log(moment().add(6, 'hours').format('YYYY-MM-DD HH:mm:ss'));//当前日期的（正数）后多少（小时、天、周、月、年）
      console.log(moment().daysInMonth());//本月有多少天
      console.log(moment().weeksInYear());//今年有多少周
      console.log(moment().endOf('week').format('YYYY-MM-DD'));//日期所在周的周六
      console.log(moment().startOf('week').format('YYYY-MM-DD'));//日期所在周的周日
      console.log(moment().year());//获取年份
      console.log(moment().weeks());//今天是第几周
      console.log(moment().hour());//日期的小时数
      console.log(moment().month());//日期的月数（需要加1）
      console.log(moment().day());//日期的星期数??
      console.log(moment().date())//日期的日数
      console.log(moment().endOf('month').format('YYYY-MM-DD HH:mm:ss'));//日期所在月的最后一天
      console.log(moment()._d);//日期的中国标准时间输出格式
      console.log(moment("20111031", "YYYYMMDD").fromNow())

    }
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
