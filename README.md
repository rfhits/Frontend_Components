# Frontend_Components
前端常用组件

## avatar

function: 点击头像，触发下拉框，里面有登陆、等出等选项。

env: vue3.0, ant-design2.2.8, element-plus

code: 

```html
<a-popover>
    <template #content>
        <el-link icon="el-icon-s-home" @click="goToPage('/home')">Home</el-link>
        <br>
        <el-link icon="el-icon-switch-button" @click="logout()">logout</el-link>
    </template>
    <a-avatar :size="40">
        <template #icon><UserOutlined /></template>
    </a-avatar>
</a-popover>
```

details:

a-popover可以将下拉菜单中的内容自动填满popover，而el-popover弹出框会太长，导致有空白。

refs

a-popover: https://2x.antdv.com/components/descriptions

el-link: https://element-plus.gitee.io/zh-CN/component/link.html

icon：https://element.eleme.cn/#/zh-CN/component/icon

## aside

function: 页面侧边栏，点击跳转，实现高亮

code: 

```vue
<template>
  <div>
    <el-menu
        router
        :default-active=this.$route.path
        class="el-menu-vertical-demo"
        style="width: 150px"
    >
      <el-menu-item index="/manage/select-course">
        <i class="el-icon-location"></i>
        <span>我要选课</span>
      </el-menu-item >
      <el-menu-item index="/manage/query-course">
        <i class="el-icon-menu" ></i>
          <span>已选课程</span>
      </el-menu-item>
    </el-menu>
  </div>
</template>
```

details: 

el-menu有router属性，点击el-menu-item时，会将el-menu-item中index作为跳转的路径

:default-active绑定到route的path属性上，我们当前的页面就是router/index.js中的routes中的一个route，有path和name属性，我们在router/index.js中写好当前页面的path，就可以直接调用this.$route.path

## comment-card

主要是组件传参的应用

```vue
<el-card :style="{width: this.cardWidth}">
  <div class="comment-time" style="color: #999">
    <ClockCircleOutlined />
    {{ cardData.date }}
  </div>

  <div class="content">
    {{ cardData.content }}
  </div>

  <div class="reply-article">
    回复帖子：{{this.cardData.articleTitle}}
  </div>

  <div style="display: flex; align-items: center; font-size: 16px">
    <LikeOutlined :style="{color:likeColor}" @click="like()"></LikeOutlined>
    <span style="color: #999; margin-left: 5px">{{ cardData.likes }}</span>
  </div>

</el-card>
```

## like

todo
