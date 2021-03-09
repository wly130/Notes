



## uniapp

### 目录

[TOC]

#### 目录结构

- **uniapp**
	- **components(目录)** **自定义组件**			
	- **pages(目录)**        **==编写页面==**
	- **static(目录)**        存放**==静态资源==**(图片,视频等)
	- **App.vue**              调用**==应用生命周期函数==**、配置**==全局样式==**和**==全局变量==**
	- **main.js**                入口文件，定义==**全局组件**==
	- **manifest.json**    **==打包==**发布配置文件
	- **pages.json**          全局配置
	- **uni.scss**               预置了**scss变量**

> #### main.js 文件
>
> - **Vue.prototype	添加==全局变量==**
>
>   ```javascript
>   Vue.prototype.$value = "value"
>   ```
>
> - **Vue.config.productionTip    是否显示生产消息**
>
> #### globalData 全局变量
>
> ```javascript
> export default {
>     globalData:{	//定义
>         value: 'value'
>     }
> }
> ```
>
> - **获取和修改 `globalData`**
>
> ```javascript
> var globalData = getApp().globalData.value;
> getApp().globalData.value = 'value2'
> ```
>
> - **在 `App.vue` 中获取 `globalData`** 
>
> ```javascript
> this.$scope.globalData.value;
> ```

#### 单位

##### 基准宽度是 ==750 rpx==

> **upx** 相对单位

- **rpx** 和 **px** 的转换
  - **rpx** = 750 \* 元素 px / 屏幕宽度 px

#### 生命周期

##### 应用生命周期

- **应用生命周期仅可在`App.vue`中监听，在其它页面监听无效。**

```javascript
onLaunch: function() { //初始化完成时
},
onShow: function() { //界面显示时(从后台进入前台显示)
},
onHide: function() { //从前台进入后台
},
onError: function() { //出现异常
}
```

##### 页面生命周期

```javascript
onLoad() { //页面加载
},
onShow() { //页面显示
},
onReady() { //页面初次渲染完成
},
onHide() { //页面隐藏
},
onUnload() { //页面卸载
}
```

[返回顶部](#目录)

#### 页面跳转

- **uni.navigateTo		保留当前页面，跳转页面**
- **uni.redirectTo	     关闭当前页面，跳转页面**
- **uni.reLaunch	       关闭所有页面，打开页面**
- **uni.switchTab	      跳转到 tabBar 页面，并关闭其他所有非 tabBar 页面**
- **uni.navigateBack   关闭当前页面，返回上一页面或多级页面**

| 参数                  | 作用                                                 |
| --------------------- | ---------------------------------------------------- |
| **success**           | **接口调用成功的回调函数**                           |
| **fail**              | **接口调用失败的回调函数**                           |
| **complete**          | **接口调用结束的回调函数（调用成功、失败都会执行）** |
| **animationType**     | **窗口显示的动画效果**                               |
| **animationDuration** | **窗口动画持续时间**                                 |

[返回顶部](#目录)

##### 窗口动画

| 显示动画        | 关闭动画         | 动画描述                                         |
| :-------------- | :--------------- | :----------------------------------------------- |
| slide-in-right  | slide-out-right  | 新窗体从右侧进入                                 |
| slide-in-left   | slide-out-left   | 新窗体从左侧进入                                 |
| slide-in-top    | slide-out-top    | 新窗体从顶部进入                                 |
| slide-in-bottom | slide-out-bottom | 新窗体从底部进入                                 |
| pop-in          | pop-out          | 新窗体从左侧进入，且老窗体被挤压而出             |
| fade-in         | fade-out         | 新窗体从透明到不透明逐渐显示                     |
| zoom-out        | zoom-in          | 新窗体从小到大缩放显示                           |
| zoom-fade-out   | zoom-fade-in     | 新窗体从小到大逐渐放大并且从透明到不透明逐渐显示 |
| none            | none             | 无动画                                           |

- **`navigateTo` 和 `redirectTo`** 只能打开**非 tabBar** 页面。
- **`switchTab`** 只能打开 **tabBar** 页面。
- **`reLaunch`** 可以打开**任意页面**。
- 页面底部的 **tabBar** 由页面决定，即只要是定义为 `tabBar` 的页面，底部都有 `tabBar`
- 不能在 **`App.vue`** 里面进行页面跳转。

#### 数据缓存

##### 异步接口[^1]

| 方法 | 作用 |
| ---- | ---- |
|**uni.setStorage**		|存储数据缓存|
|**uni.getStorage**		|读取数据缓存|
|**uni.getStorageInfo**	|获取数据缓存相关信息|
|**uni.removeStorage**	|移除数据缓存|

##### 同步接口[^2]

| 方法                       | 作用                 |
| -------------------------- | -------------------- |
| **uni.setStorageSync**     | 存储数据缓存         |
| **uni.getStorageSync**     | 读取数据缓存         |
| **uni.getStorageInfoSync** | 获取数据缓存相关信息 |
| **uni.removeStorageSync**  | 移除数据缓存         |

[^1]: 多个程序同时执行
[^2]: 上一个程序执行完再执行下一个

[返回顶部](#目录)

#### 页面通讯

- **==触发==全局的自定义事件**

  ```javascript
  uni.$emit('事件名', '参数')
  ```

- **==监听==全局的自定义事件**

  ```javascript
  uni.$on('事件名', '回调函数')
  ```

- **==监听一次==全局的自定义事件**

  ```javascript
  uni.$once('事件名', '回调函数')
  ```

- **==移除==全局的自定义事件**

  ```javascript
  uni.$off('事件名', '回调函数')
  ```
#### WebSocket
| API                       | 说明                    |
| :------------------------ | :---------------------- |
| **uni.connectSocket**     | **创建 WebSocket 连接** |
| **uni.onSocketOpen**      | **监听 WebSocket 打开** |
| **uni.onSocketError**     | **监听 WebSocket 错误** |
| **uni.sendSocketMessage** | **发送 WebSocket 消息** |
| **uni.onSocketMessage**   | **接受 WebSocket 消息** |
| **uni.closeSocket**       | **关闭 WebSocket 连接** |
| **uni.onSocketClose**     | **监听 WebSocket 关闭** |

[返回顶部](#目录)