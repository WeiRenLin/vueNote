# Vuex

### 1. 結合flux及redux

### 2. Install Vuex

```text
$ npm install vuex --save
```

### 3.在main.js宣告vuex

```javascript
// 引入 vuex
import Vuex from 'vuex'

// 告訴 Vue 使用 vuex
Vue.use(Vuex)
```

### 4. 單向資料流

```javascript
const store = new Vuex.Store({
  state: {
    count: 0
  },
  mutations: {
    increment (state) {
      state.count++
    }
  }
})
```

### 5. 操作狀態

```javascript
store.commit('increment')
```

### 6. Vuex流程

action --&gt; commit --&gt; mutation

| 步驟 | 流程描述 | 流程 |
| :--- | :--- | :--- |
| 1 | 在登入頁按下 login 按鈕 | vue |
| 2 | 按鈕觸發 action | action |
| 3 | action 調用 login API | action |
| 4 | server response success 帳號密碼正確 | action\(commit\) |
| 5 | 接收 action 資料，計算邏輯，改變狀態 | mutation |
| 6 | State 改變 ex:login: true or token: '3345678' | state |
| 7 | 轉跳到 index 頁面 | vue |

#### 

### 7. 如果需要多個state，可以使用mapState

```javascript
// 在單獨構建的版本中輔助函數為 Vuex.mapState
import { mapState } from 'vuex'

export default {
  computed: mapState({
    // 箭頭函數可使代碼更簡練
    count: state => state.count,

    // 傳字串參數 'count' 等同於 `state => state.count`
    countAlias: 'count',

    // 為了能夠使用 `this` 獲取局部狀態，必須使用常規函數
    countPlusLocalState (state) {
      return state.count + this.localCount
    }
  })
}

```

