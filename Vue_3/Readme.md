# Vue Note 3

## 學習Vue 的基礎語法
- v-on
- v-model
- components

## 範例
1. `v-on` 可以用來綁定各種事，比如 onclick...
    ```
    // bind event handler for the onclick event
    v-on:click="eventHandler"
    ```

2. `v-model` 一個雙向綁定的屬性，能夠配合`<input>`使用，將元素以及 Vue data 互相綁定
    ```
    // bind the value between the element and the Vue data
    <input v-model="message">
    ```

3. `components` 能夠在 Vue 中創建客製化的元件，並在 html 中使用
    ```
    // Difine the customized Vue component
    components: {
      "todo-item": {
        template: "<li>my customized Vue component</li>"
      }
    }
    ```

4. 透過 `props` 用來指定對應的 DOM 屬性，並將其值傳進 Vue 元件中 (要記得由於 DOM 屬性沒有大小寫區別，因此若在 Vue 中使用 Camel-Case 的命名，在 DOM attribute 需要使用對應的 kebab Case)
    ```
    // in html, we can assign the value to the attribute
    <todo-item list-data="testString"></todo-item>

    // in vue, assign the attribute listData value to the template by props
    components: {
      "todo-item": {
        props: ["listData"],
        template: "<li>{{listData}}</li>"
      }
    }
    ```

5. 結合 `v-bind` 及 `props` 便能夠使用動態的屬性值
    ```
    // in html, use v-bind to bind the attribute list-data with message, and then use it for the todo-item
    <todo-item v-bind:list-data="message"></todo-item>

    // in Vue, we set the data.message
    new Vue({
      el: "#app",
      data: {
        message: "Hello World"
      },
    })
    ```
