# vue-eleme

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

## 20170201

### 项目资源准备
1. 图标字体制作，使用iconfont [fonts](https://github.com/DengSongsong/vue-elemeApp/tree/master/src/common/fonts)
2. mock数据，模拟后台数据 [data.json](https://github.com/DengSongsong/vue-elemeApp/blob/master/data.json)
3. [移动端（手机）实现1像素下边框的方法](https://segmentfault.com/a/1190000004538413)

## 知识点总结
2. 
    `<div v-if="seller.supports" class="support">
        <span class="icon"></span>
        <span class="text">{{seller.supports[0].description}}</span>
    </div>
    `
    这里要加一个if判断，如果没加判断的话，数据可以读取出来，但是控制台还是会报错(supports[0]undefined)，因为一开始的时候在写代码的时候就把数据seller传递给了v-header组件，然后数据seller获取的过程是异步的，初始化seller是一个空对象，空对象传给v-header组件的时候，supports就是undefined，取值的时候就是undefined的，所以要判断一下，如果undefined，就不解析，也就不会报错。
3. font-size:0 消除缝隙
4. min-device-pixel-ratio
5. vertical-align: top
6. 尝试想用手机预览效果，百度了下都不能成功，花了挺多时间的，就在技术群里问了下，肯定是有人知道的，被告诉要修改配置文件，也就是config文件下面的index.js中的host属性值把localhost改成0.0.0.0这可以了，简直了，试了一下果然可以，学到了！！！！！
7.  `
        white-space nowrap
        overflow hidden 
        text-overflow ellipsis
    `
8. CSS3 filter blur(10px)
9. CSS sticky footers布局
10. 清除浮动

1. star组件完成
2. flex布局
3. vue transition
4. backdrop-filter: blur()
5. vue生命周期函数created()使用场景
5. display:table 解决垂直居中问题

1. vue nextTick()使用场景
2. vue ref
3. better-scroll js库的使用
