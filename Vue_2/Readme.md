# Vue Note 3

## 學習 Vue 的基礎語法
- v-bind
- v-if
- v-for

1. 只要加上 `v-bind` 作為元素屬性的 prefix 就能將 data 填入其中
    ```
    // bind data.message to title
    v-bind:title="message"
    ```

2. `v-if` 能夠用來判斷元素是否顯示
    ```
    // check if we show the element or not
    <div v-if="showDiv">
      show this line
    </div>
    ```

3. `v-for` 能夠用來迴圈運算
    ```
    // using for loop to create items
    <li v-for="item in list">
      {{ item.text }}
    </li>

    // and we can also add an new item in console
    app.list.push({ text: "new item string"})
    ```
