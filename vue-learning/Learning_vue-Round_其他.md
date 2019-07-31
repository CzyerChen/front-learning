> 背景：vue 2.x

### 关闭eslint校验
- 只是觉得有时候有点麻烦，因为缩进管的很严格，那本地功能性测试可以没有这个必要
- 步骤一:找到build/webpack.base.conf.js文件
- 步骤二：修改文件内容
```text
module: {
    rules: [
      ...(config.dev.useEslint ? [createLintingRule()] : []),//这边有createLintingRule()

我们需要做的就是把createLintingRule去掉就可以了
module: {
    rules: [
      ...(config.dev.useEslint ? [] : []),
```
- 然后就保存一下就可以了


### 做页面的缩放适配
- 基于 less预处理rem
```text
//定义一个变量和一个mixin（全局）
    @fontSizeBase: 75;//基于视觉稿横屏尺寸/100得出的基准font-size
    .px2rem(@name, @px){
        @{name}: @px / @fontSizeBase * 1rem;
    }
    //使用示例：
    .fontsize {
        .px2rem(fontsize, 750);
    }
    //less翻译结果：
    .fontsize {
        font-size: 10rem;
    
```
- 基于sass 预处理rem
```text
  //定义一个变量和一个mixin
    $fontSizeBase: 75;//基于视觉稿横屏尺寸/100得出的基准font-size
    @mixin px2rem($name, $px){
      #{$name}: $px / $fontSizeBase * 1rem;
    }
     
    //使用示例：
     .fontsize {
       @include px2rem(height, 750);
     }
     
    //scss翻译结果：
     .fontsize {
        font-size: 10rem;
     }
```
- 基于stylus 预处理rem
```text
  //定义一个变量和一个mixin
    $fontSizeBase: 75;//基于视觉稿横屏尺寸/100得出的基准font-size
    px2rem(name, px){
        {name}: px / $baseFontSize * 1rem;
    }
     
    //使用示例：
    .fontsize {
      px2rem('font-size', 750);
    }
     
    //stylus翻译结果：
    .fontsize {
      font-size: 10rem;
    }
```