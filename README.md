vue-picture-preview
=============

移动端Vue.js图片预览插件 | Mobile-friendly picture file preview Vue.js plugin with horizontal nav and bottom title.

[![Github](https://img.shields.io/github/stars/xLogic92/vue-picture-preview.svg?style=social&label=Star)](https://github.com/xLogic92/vue-picture-preview) [![Github](https://img.shields.io/github/forks/xLogic92/vue-picture-preview.svg?style=social&label=Fork)](https://github.com/xLogic92/vue-picture-preview) [![Github](https://img.shields.io/github/watchers/xLogic92/vue-picture-preview.svg?style=social&label=Watch)](https://github.com/xLogic92/vue-picture-preview)

[![License](https://img.shields.io/npm/l/vue-picture-preview.svg?style=flat-square)](https://www.npmjs.org/package/vue-picture-preview) [![vue-picture-preview](https://img.shields.io/npm/v/vue-picture-preview.svg?style=flat-square)](https://www.npmjs.org/package/vue-picture-preview) [![NPM downloads](http://img.shields.io/npm/dm/vue-picture-preview.svg?style=flat-square)](https://npmjs.org/package/vue-picture-preview) [![NPM downloads](http://img.shields.io/npm/dt/vue-picture-preview.svg?style=flat-square)](https://npmjs.org/package/vue-picture-preview)

![img](https://raw.githubusercontent.com/xlogic92/vue-picture-preview/master/demo.gif)

## 安装

### NPM

```sh
npm install --save vue-picture-preview
```

## 使用
首先在项目的入口文件中引入, 调用 Vue.use 安装。

```javascript
import vuePicturePreview from 'vue-picture-preview'
Vue.use(vuePicturePreview)
```

在根组件添加 lg-preview 组件的位置

```HTML
<!-- Vue root compoment template -->
<div id="app">
    <router-view></router-view>
    <lg-preview></lg-preview>
</div>
```

对于所有图片都可以使用 v-preview 指令来绑定他们的预览功能

```HTML
<img v-for="(img,index) in imgs"
     v-preview="img.url"
     :src="img.url"
     :alt="img.title"
     :key="index"
     preview-title-enable="true"
     preview-nav-enable="true">
```

```javascript
export default {
    data () {
        return {
            imgs: [
                {
                  url: 'http://covteam.u.qiniudn.com/ka2.jpg',
                  title: 'pic1'
                },
                {
                  url: 'http://covteam.u.qiniudn.com/poster.png',
                  title: 'pic2'
                }
            ]
        }
    }
}
```

```css
<style scoped>
img {
   width: 100%;
   height: 100%;
}
</style>
```

## API

* **isTitleEnable**: (boolean, optional) 设置 _preview-title-enable="false"_ 将禁用底部标题. 默认值: true.
* **isHorizontalNavEnable**: (boolean, optional) 设置 _preview-nav-enable="false"_ 将禁用水平导航. 默认值: true.
* **isCurrentAndAllTitle**：(boolean,optional) 设置 preview-title-extend=false 将底部标题(当前页/总页数)类型进行关闭(开启时isTitleEnable)将无效。默认值：true
* **isTopTitleShow**：(boolean,optional) 设置preview-top-title-tnable=false 将顶部标题禁用,默认值：true.
* **topTitle**:(string,optional) 设置data-title 设置顶部标题文本，无默认值
## update

- 新增底部标题类型(原有类型、indexPage/totalPage)
- 新增顶部标题，取设置的data-title设置的值
- 新增左右滑动切换图片
## expectation 
* 根据组来渲染预览图片的组（比如：我页面有十组想预览的，点击某一组，只预览一组的，本版本想更新，但是遇到一点小问题，需要和作者探讨下在开发） *
* 根据手指实时滑动切换图片（当前版本滑动是完成后执行切换图片，下个版本会更新实时） *
