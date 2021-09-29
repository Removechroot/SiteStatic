<template>
  <div class="hello">
    <div style="margin-bottom: 5px;">
      <input v-model="num">
      <input v-model="startTime">
      <input v-model="endTime">
    </div>
    <div class="bgc" v-for="item in parseInt(num)" :key="item">
      <span>NO:LSYY{{item.toString().length === 3? `${item}` : item.toString().length === 2? `0${item}` : `00${item}`}}</span>
      <div style="height: 110px;width: fit-content;">
      </div>
      <div style="font-size:8px;font-weight: bold;margin-left: 12px;">
        车牌号码：________；<br>
        泊车日期/时间：_____年____月____日____时____分；<br>
        取车时间：____时 ____分 ；收费员签署：<br>
        &nbsp;&nbsp;&nbsp; 本券有效期：{{startTime}}至{{ endTime }}<br>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data(){
    return{
      num:1,
      startTime:'2021年10月 1 日',
      endTime:'2021年10月31日'
    }
  },
};
</script>

<style scoped>
.hello{
  width: 100vw;
  height: auto;
}
.bgc{
  height: 181px;
  width: 300px;
  border: 2px solid #000;
  background: url("../assets/logo.png") no-repeat;
  display: inline-block;
  margin: 5px;
}
span{
  float: right;
  margin-right: 10px;
  font-size: 8px;
}
</style>
