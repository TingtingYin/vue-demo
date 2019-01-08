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
22. vue中组件复用问题
    ```
     <div id="app">
            <div v-if="show">
              用户名:  <input />
            </div>
            <div v-else>
                邮箱:  <input />
            </div>
     </div>
     
     当用户名和邮箱切换时，如果用户名已填写，那么
     邮箱出现的时候，之前的文字仍然存在。怎么解决？
     加key
    ```
23. list中最好设置一个唯一的key,性能最高，最好不要用index
24. list中通过下标操作数组，页面中的数据是不会变的
    
    什么情况下改变数组时页面也跟着变化？
    - 用变异方法，比如splice，pop,push
    - 改变数组的引用
    - set方法
    ``````


25. template与div的区别
    - template标签不显示
26. 对象循环 ： 添加对象某个属性，页面不会变。
    - 改变对象的引用才行
    - 用vue的set方法
    ```
    对象：
    Vue.set(vm.userInfo,'address','beijing')
    vm.$set(vm.userInfo,'address','beijing')
    数组：
    Vue.set(vm.list,1,5): 索引是1的值改为5
    vm.$set(vm.list,1,5)
    ```
27. table的问题
    代码：
    ```
    <body>
        <div id="app">
            <table>
                <tbody>
                    <row></row>
                    <row></row>
                    <row></row>
                </tbody>
            </table>
        </div>
        <script>
            Vue.component('row',{
                template : '<tr><td>wo</td></tr>'
            })
            var app = new Vue({
                el : '#app'
            })
        </script>
    </body>
    ```

    显示结果为：

    ```
    <body>
        <div id="app">
        <tr><td>wo</td></tr>
        <tr><td>wo</td></tr>
        <tr><td>wo</td></tr>
        <table>
            <tbody></tbody>
        </table>
        </div>
    
    </body>
    ```
    
    原因：h5的规范里，要求table里要有tbody,
   tbody里要有tr,select,ul等也是这样的问题

28. 子组件的data是个function
29. vue中怎么操作dom-div
30. vue中怎么操作dom-自定义组件