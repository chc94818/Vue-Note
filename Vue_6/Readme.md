# Vue Note 6

## 學習 Vue 的基礎語法
- v-once
- v-html
- Javascript

## 範例

1. `v-once`: Vue 預設將 DOM 內容與 data 進行雙向綁定，而 `v-once` 則可以使其內容就在最初被更新一次，且不會隨著 data 的更新而更新
    ```
    // wit v-once attribute
    <div v-once>
      <span>with v-once</span>
      <br>
      <span>{{message}}</span>
    </div>
    ```

2. `v-html`: 雙大括號中的內容會以純文字的形式插入，若想插入HTML的話需要加上 `v-html` 屬性
    ```
    // insert HTML with v-html
    <div v-html="rawHtml"></div>

    // {{value}} will only insert the pure text string
    <div>{{rawHtml}}</div>
    ```

3. Javascript 可以以單行的形式存在於模板語法中
    ```
    {{ number + 1 }}
    <div>{{ showYes && 'YES' }}</div>
    <div>{{ !showYes ? 'YES' : 'NO' }}</div>
    {{ message.split('').reverse().join('') }}
    <div v-bind:id="'list-' + id"></div>
    ```

    但並不支援下列語法
    ```
    // The statement won't work -->
    {{ var a = 1 }}

    // if statement won't work, use ternary expressions instead
    {{ if (true) { return message } }}
    ```