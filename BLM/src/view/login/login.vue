<template>
  <div id="login">
    <div class="login-wraper">
        <div class="login-card">
           <div class="left-wraper">
              <div class="left-img"></div>
           </div>
           <div class="login-form">
             <Form ref="loginForm" :model="loginForm" :rules="loginRules">
                <h1 class="login-title">教师登录</h1>
                <FormItem prop="account" class="formItem">
                  <Input v-model="loginForm.account" placeholder="请输入用户名" >
                  <Icon type="md-person" slot="prefix" size="26" color="#2D8CF0"
                  style="height: 40px;line-height: 40px;width: 40px;"/>
                  </Input>
                </FormItem>
                <FormItem prop="password" class="formItem">
                  <Input v-model="loginForm.password" type="password" placeholder="请输入密码">
                    <Icon type="md-lock" slot="prefix" size="26" color="#2D8CF0"
                  style="height: 40px;line-height: 40px;width: 40px;"/>
                  </Input>
                </FormItem>
                <FormItem prop="remember" class="formItem">
                  <Checkbox v-model="loginForm.isRemember" style="font-size: 12px;">记住我</Checkbox>
                </FormItem>
                <FormItem class="formItem">
                    <Button @click="login('loginForm')" class="login-btn" :disabled="isDisabled">登录</Button>
                </FormItem>
                <FormItem class="formItem">
                      <Checkbox @on-change="changeState" v-model="loginForm.isAgree" style="font-size: 12px;padding-left: 5px;">我已同意
                      <a calss="agreement" style="font-size: 10px;color: #999999;">《伯乐码用户服务协议》</a>                      </Checkbox>
                </FormItem>
                <FormItem class="formItem">
                    <span class="recommend" style="width:100%;height: 30px; font-size: 12px;color: #2C3E50;line-height: 30px;">推荐浏览器：
                    <i class="iconfont icon-google" style="color: #2D8CF0;font-size: 12px;">&nbsp;&nbsp;谷歌</i>
                    <i class="iconfont icon-huohu" style="color: #2D8CF0;font-size: 12px;margin-left: 15px;">&nbsp;&nbsp;火狐</i>

                    </span>
                </FormItem>
             </Form>
           </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'login',
  data(){
  	return{
        loginForm:{
          account:'',
          password:'',
          isRemember:false,
          isAgree:true,
        },
        loginRules:{
          account:[
            {required: true,message: '请输入用户名' ,tigger: 'blur'}
          ],
          password:[
             { required: true, message: '请输入密码', trigger: 'blur' },
             { type: 'string', min: 6, message: '密码长度有误', trigger: 'blur' }
          ]
        },
        isDisabled: null,
  	}
  },
  methods:{
    changeState(){
        if(this.loginForm.isAgree==false){
          this.isDisabled=true
          console.log(this.isDisabled)
        }else if(this.loginForm.isAgree==true){
          this.isDisabled=false
          console.log(this.isDisabled)
        }
    },
    noAgree(){
      if(this.loginForm.isArrgue===false){
          loginBg.style.backgroundColor = "white";
          console.log(123);
      }
    },
    login(values){
      this.$refs[values].validate((valid) => {
        if(valid){
          this.$Message.success('登录成功！');
          this.$router.push('/home')
        }else{
          this,$Message.error('账号或密码有误')
        }
      })

    }

  },
  mounted() {
    this.noAgree();
    // var run = function(){
    //   var loginBg = document.querySelector(".login-btn");
    //   if(this.loginForm.isArrgue==false){
    //     loginBg.style.backgroundColor = "White"
    //   }
    // }();


  }
};
</script>

<style scored lang="less">
@import "../../assets/style/login.less";
</style>
