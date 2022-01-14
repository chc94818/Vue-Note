# Vue Note 7

## 學習 Vue 的基礎語法
- Computed property
- Computed cache
- Computed setter

## 範例

1. 透過 `Computed property` 能夠更清楚地去使用計算後的數值，免於使用一大堆的 inline js 而造成可讀性上的影響，且 Computed function 中 `this` 會直接對應到該 vue 物件，當原始值更新時，也會重新計算並更新進 DOM 中。
    ```
    // using the computed property
    <div>Computed : "{{ reversedMessage }}"</div>
    // computed function
    computed: {
        reversedMessage: function () {
            return this.message.split('').reverse().join('')
        }
    }
    ```

2. `Computed property` 會去監聽其相依資料，並在其更新時，重新計算，但若原資料並沒有改變，則會直接使用上一次的結果，故被稱作 `Computed cache`。但若其參考的資料是物件，rerender 時則不一定會觸發更新 (若物件沒有更新，但物件內函數的返回值可能已經不同)，使用得當能夠節省大量運算，相反則需要透過 method 來實現每次 rerender 時都能夠觸發更新。
   1. 補充說明，當畫面中沒有使用到這個 `Computed data`，那麼即使他監聽的資料更新，也不會觸發計算。

3. `Computed setter`: 雖然一般而言我們只會對設定了 `computed property` 的 `getter`，但其實也能指定 `setter`，來監聽自己值的更改，並在自己更新時，去觸發後續的處理。另外 `setter` 與 `getter` 的更新是獨立的，並且 `setter` 能夠觸發 `getter`，但 `getter` 更新後不會再觸發 `setter`。
    ```
    fullName: {
        // getter
        get: function () {
            return this.firstName + ' ' + this.lastName
        },
        // setter
        set: function (newValue) {
            var names = newValue.split(' ')
            this.firstName = names[0]
            this.lastName = names[names.length - 1]
        }
    }
    ```
