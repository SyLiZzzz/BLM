<template>
  <div id="home">
    <Layout class="home-wraper">
          <heads></heads>
        </Header>
        <Layout class="home-inner">
            <Sider class="left" hide-trigger>
              <homeLeft></homeLeft>
            </Sider>
            <Content class="content">
              <index></index>
            </Content>
        </Layout>
    </Layout>
  </div>
</template>

<script>
import heads from '../../components/head.vue';
import homeLeft from '../../components/homeLeft.vue';
import index from '../../components/leftFunction/index.vue';

export default {
  name: 'home',
  data(){
  	return{

  	}
  },
  methods:{


  },
  components:{
    heads,
    homeLeft,
    index
  },
  mounted() {

  },

  }
</script>

<style scored lang="less">
  *{
    margin: 0;
    padding: 0;
  }
  html,body,#app,#home,.home-wraper{
    height: 100%;
  }
.home-inner{
  padding-top: 20px;
  padding-left: 10%;
  padding-right: 10%;
  height: 90%;
}
.content{
  height: 100%!;
  overflow-x: none!important;
}
.ivu-layout.ivu-layout-has-sider>.ivu-layout, .ivu-layout.ivu-layout-has-sider>.ivu-layout-content{
overflow-x: visible!important;
}
.left{
  background-color: white;
}

</style>
