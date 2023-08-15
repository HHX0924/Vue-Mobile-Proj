# vue-shopping
```
1.基于VueCli创建项目
2.使用vant组件库
3.postcss插件 实现vw适配
yarn add postcss-px-to-viewport@1.1.1 -D
新建postcss的配置文件postcss.config.js
4.一级路由配置
5.二级路由配置
路由出口 <router-view></router-view>
6.request模块 - axios封装
实例 请求拦截器 响应拦截器 
7.完成获取图形验证码
8.封装api接口-图形验证码
9.toast 轻提示
10.短信验证倒计时 定时器
11.封装api接口 - 登录功能
12.响应拦截器统一处理错误提示
13.将登录权证信息存入 vuex
14.vuex持久化处理
    localStorage.get/set/remove Item
15.请求拦截器添加请求 loading 效果 
16. 登录访问拦截 - 路由前置守卫
router.beforeEach((to, from, next) => {
   1. to   往哪里去， 到哪去的路由信息对象  
   2. from 从哪里来， 从哪来的路由信息对象
   3. next() 是否放行
      如果next()调用，就是放行
      next(路径) 拦截到某个路径页面
})
17.首页动态渲染
    1.封装获取首页信息的api
    2.created函数里发送请求获取信息
    3.动态渲染
    4.父传子中，传的是对象，接收时的默认值defaul是函数
        props: {
        item: {
          type: Object,
          default: () => {
            return {}
          }
        }
      }
18.搜索历史基本渲染
    1.点击搜索按钮或者地下记录都能搜索
    ①若之前没有相同的搜索，直接添加到最前面 unshit
    ②若之前有相同的搜索，先删除再添加到最前面
        indexOf判断
        splice删除
    2.清空历史
    3.搜索历史持久化
    4.跳转 传参（搜索内容）
19.搜索列表
    1.封装api
    2.this.$route.query获取参数
    3.发送请求渲染
20.商品分类页
    封装api发送请求获取数据
21.商品详情页
    封装api发送请求获取数据
    数据繁杂 先打印出来 再解构
22.加入购物车弹层
    van-action-sheet 组件
23.数字框组件
    v-modle双向绑定 = ：vlaue @input
    数据父传子
    修改 子传父
    this.$emit('input', value)     
24.加入购物车 - 判断 token 登录提示
    分析：
        1.若存在：继续加入购物车操作
        2.不存在：提示用户未登录，引导到登录页     
    Dialog组件弹出确认框
    登录后需要跳转到之前的商品详情页面 所以在跳转时传参（当前页面参数）this.$route.fullPath
    需要在登录页面进行判断是否携带参数
    this.$router.replace 和 push 的区别是：是否会产生历史记录
    左下角购物车角标商品数量
        点击加入购物车发送请求
        请求需要请求头携带token 在请求拦截器统一添加
        获取返回的数据totalCount 渲染
25.购物车-构建vuex模块 获取数据
   1.创建vuex模块 存数据
   2.动态渲染
   3.getters: 总数 选中数 价格 动态设置disabled属性（:class） 保留两小数 toFixed(2)
   4.全选反选功能
      小选带动全选
      全选带动小选
   5.数字框修改数量
     既想拿到形参 又要函数调用传参 使用箭头函数 （value）=> Fn(value,a,b)   
     封装api接口 后台更新
     vuex中aciton封装函数 页面dispatch调用
     先让页面视图更新 后让后台更新 修改obj.goods_num
```
## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
