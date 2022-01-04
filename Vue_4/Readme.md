# Vue Note 4

## 學習 Vue 的基礎語法
- Transition
- v-enter
- v-enter-active
- v-leave
- v-leave-active

## 範例
### Transition 
<img src=transition.png />

1. `v-enter`: 在元素將被顯示時自動加入元素的屬性中，只存在於第一個 frame，開始動畫之後會被移除。
2. `v-enter-active`: 在元素正在顯示的過程中，加入此屬性，完成顯示後會被移除。
3. `v-leave`: 在元素將被隱藏時自動加入元素的屬性中，只存在於第一個 frame，開始動畫之後會被移除。
4. `v-leave-active`: 在元素正在隱藏的過程中，加入此屬性，完成隱藏後會被移除。

5. class 名稱預設為 `v-{status}`，若transition元素有指定名稱的話則會是 `name-{status}`，如範例是 `fade-{status}`
    ```
    <transition name="fade">
      <p v-if="show">hello</p>
    </transition>
    ```
