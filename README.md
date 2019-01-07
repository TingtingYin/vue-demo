### vue入门示例
> vue中文文档：
https://cn.vuejs.org/v2/guide/
1. 传统dom方式say hello
2. vue方式say hello
3. 传统dom方式-定时器
4. vue方式-定时器
5. vue方式-list
6. jquery-list
    ```
    MVP : jquery方式，dom操作占了很大一部分
    MVVM : M层，V层，VM层（vue),开发集中写数据的操作即可
      
   ```
7. vue方式-全局组件-list
8. vue方式-局部组件-list 
9. vue方式-子向父传值 
10. v-bind: 可简写成 :
11. 浏览器console执行app(变量名).$destory()会销毁组件
12. 生命周期函数
    ```
    destory方法在console执行app(变量名).$destory()
    update方法在console执行app.$data.content='xx';
    ```
13. vue模板语法
    ```
    {{}}
    v-text
    v-html
    ```
14. 计算属性computed / 方法methods /监听器watch
    ```
    computed内置了缓存，当相关数据没有发生变化的时候，
    直接使用缓存
    
    methods没有内置缓存，性能没有computed好
    
    watch内置了缓存，但写法比computed复杂
    {{fullname}}
    {{mFullname()}}
    ```
15. 计算属性的get,set方法
16. vue的样式绑定-第一种方式-class-对象
17. vue的样式绑定-第二种方式-class-数组
18. vue的样式绑定-第二种方式-style-对象
19. vue的样式绑定-第二种方式-style-数组
20. vue中的条件渲染
    ```
    v-if : 如果值为false,根本不存在于dom中
    v-show : 如果值为false,在dom中，只是把display设置为none了
    ```
21. vue-if与vue-else