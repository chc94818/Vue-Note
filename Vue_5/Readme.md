# Vue Note 5

## 學習 Vue 的基礎語法
- Instance
- contructor
- extend
- data
- vm.$data
- vm.$el
- vm.$watch

## 範例

1. 建構子，及其參數 option (options 的屬性有: data, template, element to mount on(el), methods, lifecycle callbacks ...)
    ```
    var vm = new Vue({
      // options
    })
    ```

2. `extend`: 可以用來自定義建構子並加入一些預設的options
    ```
    var MyComponent = Vue.extend({
      // extension options
    })
    // all instances of `MyComponent` are created with
    // the pre-defined extension options
    var myComponentInstance = new MyComponent()
    ```

3. vue instance 會將 data 綁定到 vue instance 本身
    ```
    var data = { a: 1 }
    var vm = new Vue({
      data: data
    })
    vm.a === data.a
    // setting the property also affects original data
    vm.a = 2
    data.a === 2
    // ... and vice-versa
    data.a = 3
    vm.a === 3
    ```

4. 除了 data 外，vue 還提供了其他屬性以及函式，為了避免與 data 衝突，前面會加上 `$` 來加以區隔
    ```
    vm.$data === data
    vm.$el === document.getElementById('example')

    // $watch is an instance method
    vm.$watch('a', function (newVal, oldVal) {
      // this callback will be called when `vm.a` changes
    })
    ```

5. Instance Lifecycle
    <img src=lifecycle.png />

6. Lifecycle state
    ```
    // we can add the callback function for the lifecycle state

    var app = new Vue({
      el: "#app",
      data: {
        text: 'vue lifecycle'
      },
      created: function () {
        // `this` points to the app instance
        console.log('created with text: ' + this.text)
      },
      beforeMount: function () {
        console.log('beforeMount')
      },
      beforeDestory: function () {
        console.log('beforeDestory')
      },
      destroyed: function () {
        console.log('destroyed')
      }
    })
    ```