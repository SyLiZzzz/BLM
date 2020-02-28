<template>
  <div class="hello">
    <Button type="info" @click="toloading">
      <span v-if="!loading">点击我</span>
      <span v-else>加载中。。。</span>
    </Button>
    <Button to="//iView">Normal</Button>
    <Button to="/components/icon-en" replace>No history</Button>
    <Button to="//iviewui.com" target="_blank">New window</Button>
    <Layout>
      <Sider ref="side1" hide-trigger collapsible :collapsed-width="78" v-model="isCollapsed">
        <Menu active-name="1-2" theme="dark" width="auto" :class="menuitemClasses">
          <MenuItem name="1-1">
          <Icon type="ios-navigate"></Icon>
          <span>Option 1</span>
          </MenuItem>
          <MenuItem name="1-2">
          <Icon type="ios-search"></Icon>
          <span>Option 2</span>
          </MenuItem>
          <MenuItem name="1-3">
          <Icon type="ios-settings"></Icon>
          <span>Option 3</span>
          </MenuItem>
        </Menu>
      </Sider>
      <Layout>
        <Header :style="{padding: 0}" class="layout-header-bar">
          <Icon @click.native="collapsedSider" :class="rotateIcon" :style="{margin: '0 20px'}" type="md-menu" size="24"></Icon>
        </Header>
        <Content>Content</Content>
        <Footer>Footer</Footer>
      </Layout>
    </Layout>
    <!-- 列表 -->
    <List item-layout="vertical">
      <ListItem v-for="item in data" :key="item.title">
        <ListItemMeta :avatar="item.acatar" :title="item.title" :description="item.desc"></ListItemMeta>
        {{item.content}}
        <template slot="action">
          <li>
            <span>
              <Icon type="ios-star" v-for=" n in 4" :key="n"></Icon>
              <Icon type="ios-star" v-if="item.rate >= 9.5"></Icon>
              <Icon type="ios-star-half" v-else></Icon>
              {{item.rate}}
            </span>
          </li>
          <li>
            <Icon type="ios-star-outline"></Icon>123
          </li>
          <li>
            <Icon type="ios-thumbs-up-outline"></Icon>123
          </li>
          <li>
            <Icon type="ios-chatbubbles-outline"></Icon>123
          </li>
        </template>
        <template slot="extra">
          <img src="https://dev-file.iviewui.com/5wxHCQMUyrauMCGSVEYVxHR5JmvS7DpH/large" style="width: 280px">
        </template>
      </ListItem>
    </List>
    <Card style="width: 350px;">
      <p slot="title">
        <Icon type="ios-film-outline"></Icon>
        Classic film
      </p>
      <a href="#" slot="extra" @click.prevent="changeLimit">
        <Icon type="ios-loop-strong"></Icon>
        更多
      </a>
      <ul>
        <li v-for="item in randomMovieList">
          <a :href="item.url" target="_blank">{{item.name}}</a>
          <span>
            <Icon type="ios-star" v-for=" n in 4" :key="n"></Icon>
            <Icon type="ios-star" v-if="item.rate >= 9.5"></Icon>
            <Icon type="ios-star-half" v-else></Icon>
            {{item.rate}}
          </span>
        </li>
      </ul>
    </Card>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data() {
      return {
        loading: false,
        isCollapsed: false,
        data: [{
            title: '这是标题1',
            desc: '我是一段描述信息',
            content: '我是一段内容，我是一段内容，我是一段内容，我是一段内容',
            acatar: 'https://file.iviewui.com/dist/7dcf5af41fac2e4728549fa7e73d61c5.svg',
            rate:9.4
          },
          {
            title: '这是标题2',
            desc: '我是一段描述信息',
            content: '我是一段内容，我是一段内容，我是一段内容，我是一段内容',
            acatar: 'https://file.iviewui.com/dist/7dcf5af41fac2e4728549fa7e73d61c5.svg',
            rate:9.8
          },
          {
            title: '这是标题3',
            desc: '我是一段描述信息',
            content: '我是一段内容，我是一段内容，我是一段内容，我是一段内容',
            acatar: 'https://file.iviewui.com/dist/7dcf5af41fac2e4728549fa7e73d61c5.svg',
            rate:9.6
          }
        ],
        movieList: [{
            name: 'The Shawshank Redemption',
            url: 'https://movie.douban.com/subject/1292052/',
            rate: 9.6
          },
          {
            name: 'Leon:The Professional',
            url: 'https://movie.douban.com/subject/1295644/',
            rate: 9.4
          },
          {
            name: 'Farewell to My Concubine',
            url: 'https://movie.douban.com/subject/1291546/',
            rate: 9.5
          },
          {
            name: 'Forrest Gump',
            url: 'https://movie.douban.com/subject/1292720/',
            rate: 9.4
          },
          {
            name: 'Life Is Beautiful',
            url: 'https://movie.douban.com/subject/1292063/',
            rate: 9.5
          },
          {
            name: 'Spirited Away',
            url: 'https://movie.douban.com/subject/1291561/',
            rate: 9.2
          },
          {
            name: 'Schindlers List ',
            url: 'https://movie.douban.com/subject/1295124/',
            rate: 9.4
          },
          {
            name: 'The Legend of 1900',
            url: 'https://movie.douban.com/subject/1292001/',
            rate: 9.2
          },
          {
            name: 'WALL·E',
            url: 'https://movie.douban.com/subject/2131459/',
            rate: 9.3
          },
          {
            name: 'Inception',
            url: 'https://movie.douban.com/subject/3541415/',
            rate: 9.2
          }
        ],
        randomMovieList: []
      }
    },
    computed: {
      rotateIcon() {
        return [
          'menu-icon',
          this.isCollapsed ? 'ratate-icaon' : ''
        ];
      },
      menuitemClasses() {
        return [
          'menu-item',
          this.isCollapsed ? 'collapsed-menu' : ''
        ]
      }
    },
    methods: {
      toloading() {
        this.loading = true
      },
      collapsedSider() {
        this.$refs.side1.toggleCollapse();
      },
      // 点击改变
      changeLimit(){
        // arr->movieList
        function getArrayItems(arr,num){
          const temp_arr = []
          for(let index in arr){
            temp_arr.push(arr[index]);
          }
          const return_arr=[];
          for(let i = 0; i< num; i++){
            if(temp_arr.length>0){
              const arrIndex = Math.floor(Math.random()*temp_arr.length);
              return_arr[i] = temp_arr[arrIndex]
              temp_arr.splice(arrIndex,1)
            }else{
              break;
            }
          }
          return return_arr;
        }
        this.randomMovieList = getArrayItems(this.movieList,5);
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .menu-icon {
    transition: all .3s;
  }

  .rotate-icon {
    transform: rotate(-90deg);
  }

  .menu-item span {
    display: inline-block;
    overflow: hidden;
    width: 69px;
    text-overflow: ellipsis;
    white-space: nowrap;
    vertical-align: bottom;
    transition: width .2s ease .2s;
  }

  .menu-item i {
    transform: translateX(0px);
    transition: font-size .2s ease, transform .2s ease;
    vertical-align: middle;
    font-size: 16px;
  }

  .collapsed-menu span {
    width: 0px;
    transition: width .2s ease;
  }

  .collapsed-menu i {
    transform: translateX(5px);
    transition: font-size .2s ease .2s, transform .2s ease .2s;
    vertical-align: middle;
    font-size: 22px;
  }
</style>
