# Vue Computed & Watch區別

## 範例

```markup
<div id="app">
  <p>fullName (computed)：${ fullName }</p>
  <p>fullNameCombined (watch)：${ fullNameCombined }</p>
</div>
```

```javascript
var vm = new Vue({
  el: '#app',
  delimiters: ['${', '}'],
  data: {
    firstName: 'Bill',
    lastName: 'Chen',
    fullNameCombined: 'Bill Chen'
  },
  computed: {
    fullName: function() {
      return this.firstName + ' ' + this.lastName;
    }
  },
  watch: {
    firstName: function(val) {
      this.fullNameCombined = this.firstName + ' ' + this.lastName;
    },
    lastName: function(val) {
      this.fullNameCombined = this.firstName + ' ' + this.lastName;
    }
  }
});
```

#### 以上面的例子可以知道computed的初始值會自動計算，一旦firstName or lastName值有改變則會重新計算

#### 而watch則是需要另外在data新增一個變數\(fullNameCombined\)來手動設置fullName



