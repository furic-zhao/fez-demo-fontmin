# fez-demo-fontmin
fez-demo-fontmin 是在网页中显示艺术/特殊字体的示例，适用于开发个性化的官方网站、活动专题，提升用户浏览体验。

## 开始使用
#### 首先将fez-demo-fontmin下载到FEZ工程目录
```bash
git clone git@github.com:furic-zhao/fez-demo-fontmin.git
```
#### 进入`fez-demo-fontmin`目录

- 研发环境

```bash
gulp
```

#### 使用FEZ开发框架在网页中使用特殊字体

- 下载原始字体文件存放在`src/static/ttf/`目录中
- 收集网页中要显示特殊字体的文本
- 将文本信息放在`fez.config.js`的`minfonts`字段中，比如：

```
//fez.config.js 文件

export default {
  minFonts: `玉峰皎洁峦碧翠，龙跃奇舞云霞蔚；雪映秋色蓝月谷，山环帅气向妩媚。《忆.玉龙雪山》`
}
```

- 在项目目录执行 `gulp fontmin`
- 在项目的`src/static/fonts/`目录中会生成如下文件：

```
SentyTang.eot
SentyTang.svg
SentyTang.ttf
SentyTang.woff
SentyTang.woff2
SentyTang.less
```

以上 样式(less)内容为：

```
@font-face {
    font-family: "SentyTang";
    src: url("../fonts/SentyTang.eot"); /* IE9 */
    src: url("../fonts/SentyTang.eot?#iefix") format("embedded-opentype"), /* IE6-IE8 */
    url("../fonts/SentyTang.woff") format("woff"), /* chrome, firefox */
    url("../fonts/SentyTang.ttf") format("truetype"), /* chrome, firefox, opera, Safari, Android, iOS 4.2+ */
    url("../fonts/SentyTang.svg#SentyTang") format("svg"); /* iOS 4.1- */
    font-style: normal;
    font-weight: normal;
}
```

> 由于插件本身限制，请自行在样式文件中添加`woff2`的支持

- 在`src/static/style/`样式目录中可以使用`@import`直接引用样式文件，比如：

在`src/static/style/index.less`中引入特殊字体样式:

```
/* index.less */
@import '../fonts/SentyTang';
```

- 使用`font-family`引用字体

```
.content {
  font-family: "SentyTang";
  font-size: 50px;
}
```


> 更多开发帮助请参考[FEZ前端模块化工程开发框架](https://github.com/furic-zhao/fez)

- 实例DEMO
[fez-demo-fontmin](http://www.hestudy.com/fontmin/)

## 待续...