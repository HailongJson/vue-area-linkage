![npm-version](https://img.shields.io/npm/v/vue-area-linkage.svg) ![license](https://img.shields.io/npm/l/vue-area-linkage.svg)
# vue-area-linkage-diy
省市区联动选择. 组合数据来源：[area-data](https://github.com/dwqs/area-data)

本插件修改自vue-area-linkage(原链接地址:https://dwqs.github.io/vue-area-linkage/)

在原作者的v5.1.0上做了少量改动,实现了级联选择省市区时,选中任一级,鼠标失焦则可停止选择.


## Installation
Install the pkg with npm:
```
npm i --save vue-area-linkage-diy area-data
```
## tips
使用时只需安装vue-area-linkage-diy,其余使用方法按照原文档即可


## Usage
```
import Vue from 'vue';
import { pca, pcaa } from 'area-data'; // v5 or higher
import 'vue-area-linkage/dist/index.css'; // v2 or higher
import VueAreaLinkage from 'vue-area-linkage';

Vue.use(VueAreaLinkage)
```

```
// v5之前的版本
<area-select v-model="selected"></area-select>
<area-cascader v-model="selected2"></area-cascader>

// v5及之后的版本
<area-select v-model="selected" :data="pca"></area-select> // 省市
// 省市区：<area-select v-model="selected" :data="pcaa"></area-select>
<area-cascader v-model="selected2" :data="pca"></area-cascader> // 省市
// 省市区：<area-cascader v-model="selected2" :data="pcaa"></area-cascader>

//setting
<area-select type='all' :level='2' v-model="selected" :data="pcaa"></area-select>
<area-cascader type='all' v-model="selected2" :level='1' :data="pcaa"></area-cascader>
```

More demo to visit [here](https://dwqs.github.io/vue-area-linkage/).


## 属性
### area-select 组件
|  参数  |  类型  |  可选值  |  默认值  |  说明  |
|  :--:  |  :--:  |  :--:  |  :--:  |  :--:  |
| type | String |  all/code/text | code | 设置返回的数据格式 |
| placeholders | Array | - | [] | 设置 placeholder text |
| level | Number | 0/1/2 | 1 | 设置联动层级(0-只选省份/1-省市联动/2-省市区联动) |
| size | String | small/medium/large | medium | 设置输入框的大小 |
| disabled | Boolean | - | false | 是否禁用 |
| data | Object | - | - | 地区数据(v5需要传入) |
| icon | String | - | area-select-icon | 自定义下拉小图标 |
| disableLinkage | Boolean | - | true | 地区选择是否进行联动 |

>v4 仅支持省市区联动，即 v4 不再支持 level 的值为 3(省市区街联动)

### area-cascader 组件
|  参数  |  类型  |  可选值  |  默认值  |  说明  |
|  :--:  |  :--:  |  :--:  |  :--:  |  :--:  |
| type | String |  all/code/text | code | 设置返回的数据格式 |
| placeholder | String | - | '' | 设置 placeholder text |
| level | Number | 0/1 | 0 | 设置联动层级(0-省市联动/1-省市区联动) |
| size | String | small/medium/large | medium | 设置输入框的大小 |
| separator | String | - | '-' | 显示选中文本的分隔符 |
| disabled | Boolean | - | false | 是否禁用 |
| data | Object | - | - | 地区数据(v5需要传入) |

## 事件

|  事件名  |  说明  |  参数 |
|  :--:  |  :--:  |  :--: |
| change | 选中值发生变化时触发 | 目前选择的值 |

> change 事件在 1.2.5 之后提供

## Related Project
* [react-area-linkage](https://github.com/dwqs/react-area-linkage)
## License
MIT.
