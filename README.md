# luffy

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

For detailed explanation on how things work, consult the [docs for vue-loader](http://vuejs.github.io/vue-loader).

### 功能：首页、课程、微职位、深科技
> VUE
    - 课程列表 :this.axios + this/that
    - 课程详细 : this.axios + this/that
    - 推荐课程: this.axios
    - 用户登录：
        > this.axios
        > this
        > 跨域简单和复杂请求
        > vuex做全局变量
        > vue-cookies
    - 微职位
        > 拦截器
        > 携带token
        PS:api可以统一放在store保存
    - 深科技
        > 文章列表
        > 文章详细
        > 文章评论
        > 点赞
        > 收藏
> API
> - 课程列表
>     + 序列化：source = 'get_level_display'
> - 课程详细：
>     + 序列化：source = 'get_level_display'
>     + 序列化：method
> - 用户登录
>     + update_or_create
> - 微职位
>     + 认证组件
>  - 关联组件：
>      + 版本
>      + 解析器
>      + 渲染器
>      + 序列化
>      + 认证组件
>      + 视图
>      + 路由