# 验证码对应的 Unity package 工程

## 使用方法

下载并解压出 captcha-plugin-u3d.unitypackage，在 Assets 目录右键选择 Import Package 导入 captcha-plugin-u3d.unitypackage 资源包

其中 Test.cs 是调用示例代码

## iOS 导入NTESVerifyCodeResources.bundle到工程中：

进入`Build Phase`，在`Copy Bundle Resources`选项中，添加`NTESVerifyCodeResources.bundle`文件(请勾选Copy items if needed选项) 。

## 所有 Api

## Android

### 初始化
```
Init(Options options)
```
Options 是配置项

#### Options配置项说明：
*   入参说明：

    |参数|类型|是否必填|默认值|描述|
    |----|----|--------|------|----|
    | captcha_id | string | 是 | 无 | 易盾分配的业务 id |
    | debug | bool | 否 | false | 是否debug模式，debug模式有详细日志 |
    | is_hide_close_button | boolean | 否 | false | 是否隐藏关闭按钮 |
    | use_default_fallback | boolean | 否 | true | 是否采用默认降级 |
    | is_touch_outside_disappear | boolean | 否 | true | 点击弹窗外部是否可关闭 |
    | dimAmount | float | 否 | 0.5 | 遮罩层透明度 |
    | timeout | int | 否 | 3000ms | 超时时间 |
    | failed_max_retry_count | short | 否 | 3 | 失败后默认尝试次数 |
    | language_type | string | 否 | 系统语言 | 多语言类型 |
    | protocol | string | 否 | 无 | 资源加载协议，支持http和https |
    | is_ipv6 | bool | 否 | false | 网络是否ipv6 |
    | loading_text | string | 否 | 无 | 加载中弹窗的加载文案 |
    | extraData | string | 否 | 无 | 额外参数 |
    | is_close_button_bottom | bool | 否 | false | 关闭按钮是否在下方 |
    | is_show_loading | bool | 否 | true | 是否显示加载中弹窗 |
    | is_mourning_day | bool | 否 | false | 是否开启黑白模式 |
    | size | string | 否 | 无 | 字体大小，支持small、medium、large、x-large |
    | apiServer | string | 否 | 无 | 私有化接口域名 |
    | staticServer | string | 否 | 无 | 私有化资源域名 |
    | is_show_inner_close | bool | 否 | false | 是否显示验证码内部关闭按钮 |
    | can_upload | bool | 否 | true | 是否支持数据上报 |
    | keycode_back_enable | bool | 否 | true | 物理返回键是否可用 |
    | ui_params_json | string | 否 | 无 | 高级ui json字符串 |
	
#### language_type 支持78种语言

| 多语言值 | 说明 |
| ---- | ---- |
| zh-TW | 中文繁体 |
| en | 英文 |
| ja | 日语 |
| ko | 韩文 |
| th | 泰语 |
| vi | 越南语 |
| fr | 法语 |
| ru | 俄语|
| ar | 阿拉伯语 |
| de | 德语 |
| it | 意大利语 |
| he | 希伯来语 |
| hi | 印地语 |
| id | 印尼语 |
| my | 缅甸语 |
| lo | 老挝语 |
| ms | 马来语 |
| pl | 波兰语 |
| pt | 葡萄牙语 |
| es | 西班牙语 |
| tr | 土耳其语 |
| nl | 荷兰语 |
| es-la | 拉美西语 |
| pt-br | 巴西葡语 |
| sv | 瑞典语  |
| no | 挪威语  |
| da | 丹麦语  |
| cs | 捷克语  |
| hu | 匈牙利语  |
| sk | 斯洛伐克语  |
| ro | 罗马尼亚语  |
| el | 希腊语  |
| sr | 塞尔维亚语  |
| bs | 波斯尼亚语  |
| mk | 马其顿语  |
| bg | 保加利亚语  |
| fi | 芬兰语   |
| et | 爱沙尼亚语   |
| lv | 拉脱维亚语   |
| lt | 立陶宛语   |
| sl | 斯洛文尼亚语    |
| hr | 克罗地亚语    |
| uk | 乌克兰语   |
| vi | 越南语    |
| fa | 波斯语    |
| ca | 加泰罗尼亚语    |
| gl | 加利西亚语     |
| eu | 巴斯克语     |
| ka | 格鲁吉亚语     |
| az | 阿塞拜疆语     |
| uz | 乌兹别克语     |
| km | 高棉语     |
| si | 僧伽罗语     |
| ur | 乌尔都语     |
| bo | 藏语     |
| be | 白俄罗斯语     |
| kk | 哈萨克语（西里尔文）     |
| bn | 孟加拉语     |
| fil | 菲律宾语     |
| jv | 爪哇语     |
| ne | 尼泊尔语     |
| sw | 斯瓦西里语     |
| mi | 毛利语     |
| am | 阿姆哈拉语     |
| te | 泰卢固语     |
| mr | 马拉地语     |
| ta | 泰米尔语     |
| gu | 古吉拉特语     |
| kn | 卡纳达语     |
| ml | 马来亚拉姆语     |
| or | 欧里亚语     |
| pa | 旁遮普语     |
| as | 阿萨姆语     |
| mai | 迈蒂利语     |
| mn | 蒙古语（西里尔文）     |
| ug | 维吾尔语     |

####
高级 ui 配置

<img src="https://github.com/yidun/captcha-android-demo/blob/master/screenshots/Popup.png">
<img src="https://github.com/yidun/captcha-android-demo/blob/master/screenshots/Custom.png">

json 字段支持范围如下

```
{
   "customStyles":{
       "imagePanel":{
           "align":"top", // 仅在 float 模式下有效，可选项为 top 和 bottom，指定 imagePanel 出现在 controlBar 上方还是下方
           "borderRadius":"2px", // 边框圆角大小，当传入数字时，默认单位 px；当传入字符串时，支持单位 px、rem、em、%
           "loadBackgroundImage":"xxx", // 加载中时的背景图片地址，v2.21.4 后新增，需要填入一个 url
           "loadBackgroundColor" :"#f00"  // 加载中时的背景颜色，v2.21.4 后新增，支持 CSS 所有颜色值
       },
       "controlBar":{
          "height": "40px", // 高度，当传入数字时，默认单位 px；当传入字符串时，支持单位 px、rem、em，不支持 %，会影响功能
          "borderRadius": "20px", // 边框圆角大小，当传入数字时，默认单位 px；当传入字符串时，支持单位 px、rem、em、%
          "paddingLeft": "40px", // 左边距，如果相对于整个 bar 居中提示文字，设为 0； v2.21.4 后新增，当传入数字时，默认单位 px；当传入字符串时，支持单位 px、rem、%，不支持 em，会影响功能
          "borderColor": "transparent", // 边框颜色，支持 CSS 所有颜色值
          "background": "#e1c1ff", // 背景颜色，占满整个 controlBar，支持 CSS 所有颜色值
          "borderColorMoving": "#0000ff", // 滑动时已滑动区域边框、滑块颜色，仅在滑动类型验证码下有效，支持 CSS 所有颜色值
          "backgroundMoving": "rgba(0, 0, 255, 0.1)", // 滑动时已滑动区域背景颜色，仅在滑动类型验证码下有效，支持 CSS 所有颜色值
          "borderColorSuccess": "#00ff00", // 验证成功时边框、文字、滑块背景颜色，如果是滑动，已滑动区域有效，支持 CSS 所有颜色值
          "backgroundSuccess": "rgba(0, 255, 0, 0.1)", // 验证成功时背景颜色，如果是滑动，已滑动区域有效，支持 CSS 所有颜色值
          "borderColorError": "#ff0000", // 验证失败时边框、文字、滑块背景颜色，如果是滑动，已滑动区域有效，支持 CSS 所有颜色值
          "backgroundError": "rgba(255, 0, 0, 0.1)", // 验证失败时背景颜色，如果是滑动，已滑动区域有效，支持 CSS 所有颜色值
          "slideBackground": "#fff", // 滑块滑动前背景颜色，支持 CSS 所有颜色值
          "textSize": "14px", // 滑块内文本大小，当传入数字时，默认单位 px；当传入字符串时，支持单位 px、rem，不支持 em、%，会影响功能
          "textColor": "orange", // 滑块内文本颜色（滑块滑动前、失败、成功前的颜色），支持 CSS 所有颜色值
          "slideIcon": "", // 滑块滑动前 iocn，需要是一个 url，如果未提供则按照默认icon显示
          "slideIconMoving": "", // 滑块滑动过程 iocn，需要一个 url，如果未提供则按照默认 icon 显示
          "slideIconSuccess": "", // 滑块验证成功时 iocn，需要一个 url，如果未提供则按照默认 icon 显示
          "slideIconError": "" // 滑块验证失败时 iocn，需要一个 url，如果未提供则按照默认 icon 显示                          
       },
        "icon": {
          "intellisenseLogo": "" // 智能无感知的 icon，需要一个 url，如果未提供则按照默认 icon 显示
       },
        "gap": "30px", // imagePanel 相对 controlBar 的间距大小，当传入数字时，默认单位 px；当传入字符串时，支持单位 px、rem、em、%
        "executeBorderRadius": "4px", // imagePanel 右边顶部的操作按钮最外层容器圆角大小，当传入数字时，默认单位 px；当传入字符串时，支持单位 px、rem、em、%
        "executeBackground": "rgba(0, 0, 0, 0.2)", // imagePanel 右边顶部的操作按钮最外层容器背景颜色，支持 CSS 所有颜色值
        "executeTop": "4px", // imagePanel 右边顶部的操作按钮最外层容器顶部距离，当传入数字时，默认单位 px；当传入字符串时，支持单位 px、rem、em、%
        "executeRight": "4px" // imagePanel 右边顶部的操作按钮最外层容器右侧距离，当传入数字时，默认单位 px；当传入字符串时，支持单位 px、rem、em、%
   }，
   "popupStyles":{
        "width": "350px", // 宽度，当传入数字时，默认单位 px；当传入字符串时，支持单位 px、%，v2.21.4 后支持 rem、em
        "capBarHeight": "50px", // 弹框头部标题所在容器高度，当传入数字时，默认单位 px；当传入字符串时，支持单位 px，v2.21.4 后支持 rem；不支持 %、em，会影响功能
        "capBarTextAlign": "left", // 弹框头部标题文字对齐方式，可选值为 left、center、right
        "capBarBorderColor": "#fff",  // 弹框头部标题下边框颜色，想要去掉的话可取 transparent 或者与背景色同色，支持 CSS 所有颜色值
        "capBarTextColor": "#333", // 弹框头部标题文字颜色，支持 CSS 所有颜色值
        "capBarTextSize": 14, // 弹框头部标题文字字体大小，当传入数字时，默认单位 px；v2.21.4 后支持字符串，单位 px、rem；不支持 %、em，会影响功能
        "capBarTextWeight": 600, // 弹框头部标题文字字体体重，可设置粗细，也就是 css 样式的 font-weight 属性
        "capPadding": 15, //  弹框 imagePanel 与外边框距离，相当于总体设置 capPaddingTop，capPaddingRight，capPaddingBottom，capPaddingLeft，当传入数字时，默认单位 px；当传入字符串时，支持单位 px；不支持 %、rem，em，如果传入的单位是 %、rem、em 时，保留数字并强转为 px 单位
        "capPaddingTop": 0, // 弹框 imagePanel 与上外边框距离，会覆盖 capPadding 上边距，当传入数字时，默认单位 px；v2.21.4 后支持字符串，单位 px，如果传入的单位是 %、rem、em 时，保留数字并强转为 px 单位
        "capPaddingRight": 15, // 弹框 imagePanel 与右外边框距离，会覆盖 capPadding 右边距，当传入数字时，默认单位 px；v2.21.4 后支持字符串，单位 px，如果传入的单位是 %、rem、em 时，保留数字并强转为 px 单位
        "capPaddingBottom": 0, // 弹框 imagePanel 与下外边框距离，会覆盖 capPadding 下边距，当传入数字时，默认单位 px；v2.21.4 后支持字符串，单位 px，如果传入的单位是 %、rem、em 时，保留数字并强转为 px 单位
        "capPaddingLeft": 15, // 弹框 imagePanel 与左外边框距离，会覆盖 capPadding 左边距，当传入数字时，默认单位 px；v2.21.4 后支持字符串，单位 px，如果传入的单位是 %、rem、em 时，保留数字并强转为 px 单位
        "opacity": 0.1, // 弹框遮罩层透明度,0 ~ 1 之间的数字
        "radius": 20, // 弹框最外层容器圆角，当传入数字时，默认单位 px；v2.21.4 后支持字符串，单位 px、%、rem，em
        "borderColor": "transparent", // 弹框最外层容器边框颜色，想要去掉的话可取 transparent 或者与背景色同色，支持 CSS 所有颜色值
        "paddingTop": 20, // 弹框最外层容器上内边距，实践时可与 capPaddingTop 配合，当传入数字时，默认单位 px；v2.21.4 后支持字符串，单位 px、%、rem，em
        "paddingBottom": 40, // 弹框最外层容器下内边距，实践时候可与 capPaddingBottom 配合，当传入数字时，默认单位 px；v2.21.4 后支持字符串，单位 px、%、rem，em
        "position": "absolute", // 弹框的 css 定位，可填 absolute、fixed、static 等，默认时 absolute
        "top": "20%" // 弹框相对顶部的位置，也就是 css 样式的 top 属性   
   }，
   "customTexts":{
        "slideTip": "向右拖动滑块填充拼图" // 滑动模块文案      
   }
}
```

### 显示验证码

```
ShowCaptcha()
```

