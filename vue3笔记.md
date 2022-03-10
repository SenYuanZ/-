# vue3记录笔记

#### vue3生态

1. Vite构建工具
2. `<script setup>`
3. Volar 的使用
4. vue-tsc 检查生成
5. Pinia 新状态管理





#### setup中使用生命周期函数

如果要在setup方法中调用组件[生命周期](https://so.csdn.net/so/search?q=生命周期&spm=1001.2101.3001.7020)钩子函数:在原来的生命周期钩子函数名称前加on关键字,并且需要保持小驼峰的命名方式。

![image-20220309112143195](C:\Users\鸢泽童话\AppData\Roaming\Typora\typora-user-images\image-20220309112143195.png)



<font color=red>**不能在setup方法中调用beforeCreate, created者2个生命周期钩子函数！ 解释：(因为beforecreate, created这两个生命周期钩子函数的执行时间和setup方法接近）**</font>

```
import {onMounted, onUpdated} from 'vue'
 
export default {
  name: "Lifecycle",
  setup() {
    onMounted(() => {
      console.log("组件视图挂载完成")
    });
    onUpdated(() => {
      console.log("组件更新完成")
    });
  }
}
```





