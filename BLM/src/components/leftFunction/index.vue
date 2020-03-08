<template>
  <div id="index">
    <div class="wraper">
      <div class="today">
        <h2>今日备课</h2>
        <div class="classCard">
          <h2 class="time">{{time}}</h2>
          <p>暂无课程信息</p>
         <p style="margin-top: 25px;"><Icon type="ios-apps-outline" size="22"/></p>
        </div>
      </div>
      <div class="tomorrow">
        <h2>明日备课</h2>
        <div class="classCard">
          <h2 class="time">{{time}}</h2>
          <p>暂无课程信息</p>
           <p style="margin-top: 25px;"><Icon type="ios-apps-outline" size="22"/></p>
        </div>
      </div>
      <div class="classManage">
        <div class="classTitle">班级管理</div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'index',
    data(){
      return{
        time: "2020-03-09"
      }
    }
  }
</script>

<style scoped lang="less">
@import "../../assets/style/index.less";
</style>
