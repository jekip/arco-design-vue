```yaml
meta:
  type: 组件
  category: 数据输入
title: 输入框 Input
description: 基本表单组件，并在原生控件基础上进行了功能扩展，可以组合使用。
```

@import ./__demo__/basic.md

@import ./__demo__/status.md

@import ./__demo__/size.md

@import ./__demo__/prefix.md

@import ./__demo__/prepend.md

@import ./__demo__/word-limit.md

@import ./__demo__/group.md

@import ./__demo__/search.md

@import ./__demo__/search-loading.md

@import ./__demo__/password.md


### `<input>` Props

|参数名|描述|类型|默认值|
|---|---|---|:---:|
|model-value **(v-model)**|绑定值|`string`|`-`|
|default-value|默认值（非受控状态）|`string`|`''`|
|size|输入框大小|`'mini' \| 'small' \| 'medium' \| 'large'`|`'medium'`|
|allow-clear|是否允许清空输入框|`boolean`|`false`|
|disabled|是否禁用|`boolean`|`false`|
|readonly|是否为只读状态|`boolean`|`false`|
|error|是否为错误状态|`boolean`|`false`|
|placeholder|提示文字|`string`|`-`|
|max-length|输入值得最大长度|`number`|`-`|
|show-word-limit|是否显示字数统计|`boolean`|`false`|
|word-length|字符长度的计算方法|`(value: string) => number`|`-`|
### `<input>` Events

|事件名|描述|参数|
|---|---|---|
|input|用户输入时触发|-|
|change|仅在输入框失焦或按下回车时触发|-|
|press-enter|用户按下回车时触发|-|
|clear|用户点击清除按钮时触发|-|
|focus|输入框获取焦点时触发|-|
|blur|输入框失去焦点时触发|-|
### `<input>` Methods

|方法名|描述|参数|返回值|
|---|---|---|---|
|focus|使输入框获取焦点|-|-|
|blur|使输入框失去焦点|-|-|
### `<input>` Slots

|插槽名|描述|参数|
|---|:---:|---|
|append|后置标签|-|
|prepend|前置标签|-|
|suffix|后缀元素|-|
|prefix|前缀元素|-|








### `<input-password>` Props

|参数名|描述|类型|默认值|
|---|---|---|:---:|
|invisible-button|是否显示可见按钮|`boolean`|`true`|




### `<input-search>` Props

|参数名|描述|类型|默认值|
|---|---|---|:---:|
|search-button|是否为后置按钮模式|`boolean`|`false`|
|loading|是否为加载中状态|`boolean`|`false`|
|size|输入框大小|`'mini' \| 'small' \| 'medium' \| 'large'`|`'medium'`|
### `<input-search>` Events

|事件名|描述|参数|
|---|---|---|
|search|单击搜索按钮时触发|value: `string`|


