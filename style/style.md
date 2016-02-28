### 样式声明
声明用`StyleSheet.create`
    
    var styles = StyleSheet.create({
        base: {
            width: 38,  //单位为pt
            height: 38,
        },
        bg: {
            backgroundColor: '#223344',
        },
    })

    建议样式只产生一次，而不是在每次render时产生。

    // pt是Point，印刷行业常用单位，等于1/72英寸
    // px 是相对大小，代表像素.
    // PPI (DPI): 每英寸的像素 px/inch 如果是72dpi，则1pt = 1px，进行转换就行
    
    PixelRatio.get() 获取的是像素比率。如果宽为200，则对应的像素值为为200 * PixelRatio.get()
    设置最小单位为1/PixelRatio.get()

### 样式的使用

    
    <Text style={styles.base} />

    <View style={[styles.base, styles.bg]} />

    <View style={[styles.base, this.state.active && styles.bg]} />

    <View style={{
        width: 100,
        height: 100,
    }} />

    <View style={[styles.base, {
        width: 200,
        height: 200,
    }]}

### 组件常用的flexbox属性

### View常用的style
    具体看https://facebook.github.io/react-native/docs/view.html#style 

    borderColor, borderXColor
    borderWidth, borderXWidth 
    borderRadius, borderXRadius 
    opacity, overflow...

### Image的相关属性 
    具体看https://facebook.github.io/react-native/docs/image.html#style 
    resizeMode  ['cover'|'contain', 'stretch']


### Text的相关属性
    具体看https://facebook.github.io/react-native/docs/text.html#style 
    color
    fontFamily fontSize fontStyle fontWeight 
    lineHeight textAlign 
    textShadowColor textShadowOffset textShadowRadius 
    [for ios] letterSpacing, textDecorationColor, textDecorationLine...
    [for android] textAlignVertical

### Transforms相关的属性
    具体看https://facebook.github.io/react-native/docs/transforms.html#content

