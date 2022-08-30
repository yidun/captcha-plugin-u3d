# 验证码对应的 Unity package 工程

## 使用方法

下载并解压出 captcha_u3d.unitypackage，在 Assets 目录右键选择 Import Package 导入 captcha_u3d.unitypackage 资源包

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
    | is_no_sense_mode | boolean | 否 | false | 是否智能无感知 |
	| is_hide_close_button | boolean | 否 | false | 是否隐藏关闭按钮 |
	| use_default_fallback | boolean | 否 | true | 是否采用默认降级 |
	| is_touch_outside_disappear | boolean | 否 | true | 点击弹窗外部是否可关闭 |
	| dimAmount | float | 否 | 0.5 | 遮罩层透明度 |
	| timeout | int | 否 | 3000ms | 超时时间 |
	| failed_max_retry_count | short | 否 | 3 | 失败后默认尝试次数 |
	| language_type | string | 否 | 系统语言 | 多语言类型 |
	
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

### 显示验证码

```
ShowCaptcha()
```

