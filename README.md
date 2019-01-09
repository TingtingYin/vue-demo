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
31. 父组件向子组件传值
    - :count="0" 传递的是数字
    -  count="0" 传递的是字符串
    - 子组件不能修改父组件传的值,只能创建副本，修改副本
32. 父组件通过[属性]的形式向子组件传值,
    子组件通过[事件触发]的形式向父组件传值
33. 组件参数校验  
34. 组件参数校验细节
    pros特性：父向子传递的属性是不会在便签显示的，
    比如：connt="12a555"
35. 给组件绑定原生事件:@click.native
36. 非父子组件间传值（Bus/总线/发布订阅模式/观察者模式）
37. 父向子传递的html解析不出
    ````
    <div v-html="this.content"></div>
    这里不能用template
    ```
38. slot-父向子传递dom
39. 作用域插槽
40. 动态组件
41. v-once:可以提高效率
    动态组件不停地创建组件，销毁组件，而v-once把组件放内存中，
    下次就不用创建了，提高性能
42. transition动画
 如果transition name='fade',则这里可以写成.fade-enter
43. vue使用animate.css库
    - @keyframes的bounce动画
44. 动画的样式名称可以自定义
45. 使用animate.css库
46. vue中同时使用过渡和动画
    - （解决第一次显示没有动画）
    - 同时使用过渡和动画( type="transition"以transition设定的时常为准，这里是3s,而animate.css默认时常为1s)
    - 自定义动画时长（到了时间，动画加的class才会消失）
47. 使用js实现动画
    - @before-enter ： 从没有到有的时候触发
    - @enter
    - @after-enter
    - 效果： 2秒后变绿，4秒后变黑
    ------- leave同上
    - 使用velocity.js实现动画
48. 多个元素的动画
    - 由于组件的复用，切换的时候动画会失效，要用key
    - mode="in-out" "out-in"等
49. 动态组件-动画
48. 列表-过渡动画
49. 动画封装1