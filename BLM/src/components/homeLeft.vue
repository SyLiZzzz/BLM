<template>
  <div id="homeLeft">
    <div class="leftCard">
      <div class="leftUser">
        <div class="userImg-box">
          <img class="userImg" src="../assets/home-img/logologo.png"/>
        </div>
        <p class="leftUser-name">{{username}}</p>
        <p class="lestUser-title">暂未设置个人标签</p>
        <Button class="toClass">去上课</Button>
        <div class="userFunction">
          <p class="change-password"><Icon type="ios-unlock-outline" size="16" />修改密码</p>
          <p class="myNews"><Icon type="ios-notifications" color="#ffc700" size="16" />我的消息</p>
        </div>
      </div>
      <div class="leftFunction">
        <Menu>
            <MenuItem name="myInfor" class="items">
              <Icon type="ios-home-outline"  size="22"/>
              个人中心
            </MenuItem>
            <MenuItem name="addTest" class="items">
              <Icon type="ios-paper-outline"  size="22"/>
              添加考试
            </MenuItem>
            <MenuItem name="addClass" class="items">
              <Icon type="md-bookmarks"  size="22"/>
              添加课程
            </MenuItem>
            <MenuItem name="addMuBan" class="items">
              <Icon type="ios-calendar-outline"  size="22"/>
              添加模板
            </MenuItem>
            <MenuItem name="addJiHua" class="items">
              <Icon type="ios-clipboard-outline"  size="22"/>
              添加计划
            </MenuItem>
            <MenuItem name="addReport" class="items">
              <Icon type="ios-megaphone-outline" size="22" />
              学习报告
            </MenuItem>
        </Menu>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'homeLeft',
    data(){
      return{
        username:'测试用户001'
      }
    },
    methods:{

    },
    mounted() {
      let that = this;
      var leftUl = document.querySelector('.ivu-menu');

      function loadTree(parent,callback){
        for(var i =0; i <parent.children.length;i++){
          var child = parent.children[i];
          if(callback){
            callback(child)
          }
        }
      }

    loadTree(leftUl,function(ele){
      ele.onclick = function(){
        for(var i=0 ; i< leftUl.children.length;i++){
          leftUl.children[i].calssName = "noLiBorder"
        }
        this.className = "liBorder"
      }
    })

    }
  }
</script>

<style scoped lang="less">
  @import "../assets/style/left.less";
</style>
