<template>
  <div id="login">
    <div id="bg">
      <Row type="flex" justify="center" align="middle" class="code-row-bg">
        <Col span="10">
        <div class="loginform">
          <Row type="flex" justify="start" class="loginform-row">
            <Col span="11" offset="1">
            <div class="login-bg"></div>
            </Col>
            <Col offset="1" span="10" class="loginform-row-in">
            <h1>教师登录</h1>
            <Input prefix="md-person" class="i-input" size="large" clearable placeholder="请输入用户名" style="color: #2D8CF0; background-color: #fff8c6;" />
            <Input prefix="ios-contact" class="i-input" type="password" size="large" clearable placeholder="请输入密码" />
            <Row type="flex" justify="start">
              <Col span="6" pull="1">
                <Checkbox v-model="single" size="small" style="color: #2c3e50;font-size: 12px; margin-top: 25px;">记住我</Checkbox>
              </Col>
            </Row>
            <Button type="primary" long shape="circle" size="large" style="font-size: 12px; margin-top: 15px;">登录</Button>
            <Row type="flex" justify="start">
              <Col span="20" pull="2" >
                <Checkbox v-model="check" size="small" style="color: #2c3e50;font-size: 12px; margin-top: 15px;">我已同意<span style="color: #999;;">《伯乐码用户服务协议》</span></Checkbox>
              </Col>
            </Row>
            <Row type="flex" justify="start">
              <Col>
                <br />
              <p>
                <span style="font-size: 12px; color: #2c3e50;">推荐浏览器：</span>
                <a href="https://www.google.cn/chrome/" class="outer-chain"> <i class="icon-iconset0284 iconfont"></i>谷歌</a>
                <a href="http://www.firefox.com.cn/" class="outer-chain"> <i class="iconfont icon-huohu"></i>火狐</a>
              </p>
              </Col>
            </Row>
            </Col>
          </Row>
        </div>
        </Col>
      </Row>
    </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        single: false,
        check: true
      }
    },
    components: {

    },
    computed: {

    },
    methods: {

    },
    mounted() {

    }
  }
</script>

<style scoped="scoped">
  #login {
    padding: 0px;
    margin: 0px;
  }

  #bg {
    background-image: url(../assets/img/login/bg.png);
    background-size: 100% 100%;
    background-repeat: no-repeat;
    width: 100%;
    height: 944px;
  }

  #login #bg .code-row-bg {
    height: 100%;
  }

  #login #bg .code-row-bg .loginform {
    background-color: white;
    box-shadow: 0 0 5px rgba(0, 0, 0, .2);
    border-radius: 20px;
    width: 740px;
    height: 400px;
  }

  #login #bg .code-row-bg .loginform .loginform-row {
    height: 85%;
  }

  #login #bg .code-row-bg .loginform .loginform-row .login-bg {
    margin-top: 30px;
    width: 100%;
    height: 95%;
    box-shadow: 1px 1px 3px 0 rgba(0, 0, 0, .15);
    border-radius: .2rem;
    background-image: url(../assets/img/login/img.jpg);
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
  #login #bg .code-row-bg .loginform .loginform-row .loginform-row-in {
    color: #2d8cf0;
    text-align: center;
    font-size: 12px;
    margin-top: 30px;
  }
  #login #bg .code-row-bg .loginform .loginform-row .loginform-row-in .i-input{
    margin-top: 25px;
    height: 42px;
  }
</style>
