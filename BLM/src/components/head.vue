<template>
  <div id="heads">
      <Header class="head">
      <div class="left-logo">
        <img class="logo-img" src="../assets/home-img/bolema_logo_0923_white.png" />
      </div>
      <div class="head-center">
        <ul class="firstUl">
          <li>首页</li>
          <li>班级</li>
          <li>考试</li>
          <li>课程</li>
          <li>题库</li>
          <li>上课</li>
          <li>进度计划模板</li>
          <li>进度计划管理</li>
        </ul>
      </div>
        <div class="head-right">
          <div class="right-line"></div>
          <div class="img-box">
            <img class="head-img" src="../assets/home-img/logologo.png" />
          </div>
          <Dropdown trigger="click" style="color: white;width: 100px;margin-right: 100px;">
                  <a href="javascript:void(0)" style="color: white;">
                      {{username}}
                      <Icon type="ios-arrow-down"></Icon>
                  </a>
                  <DropdownMenu slot="list">
                      <DropdownItem style="text-align: center;font-size: 12px!important;" name="logout" on-click="">退出登录</DropdownItem>
                  </DropdownMenu>
              </Dropdown>
        </div>
    </Header>
  </div>
</template>

<script>
  export default {
    name: 'heads',
    data(){
      return{
        username:'测试用户001'
      }
    },
    methods:{
      logout(){
          this.$router.push('/');
        },
    },
    mounted() {
      let that = this;
        //退出______
        var logouts = document.querySelector('.ivu-dropdown-item');
        var headUl = document.querySelector('.firstUl');
        logouts.onclick = function(){
          that.logout();
        }
        //______

        //循环遍历顶部选项卡的子元素    ul>li______
        function loadTree(parent,callback){
          for(var i = 0; i < parent.children.length;i++){
            var child = parent.children[i];
            if(callback){
              callback(child)
            }
          }
        }
        // 选项卡点击添加边框底部样式
        loadTree(headUl,function(element){
          element.onclick = function(){
            // 点击前先将所有子元素的样式统一
            for(var i = 0; i < headUl.children.length;i++){
              headUl.children[i].className = "noStyle"
            }
            // 给点击选中的选项卡添加新样式
            this.className = "bottmStyle"
          }
        })
      }
      //_______
    }
</script>

<style scoped lang="less">
@import "../assets/style/head.less";
</style>
