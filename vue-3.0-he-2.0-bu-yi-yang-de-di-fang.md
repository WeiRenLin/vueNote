# vue 3.0和2.0不一樣的地方

1.Function-based Component API\(Composition API\)

vue 2.0對於邏輯的寫法

```javascript
export default {
  data() {
    return {
      todo: "",
      items: ["Vue", "is", "Awesome"]
    };
  },
  methods: {
    // Add: Click Handler Function
    add() {
      if (this.todo) {
        this.items.push(this.todo);
        this.todo = "";
      }
    },
    //Remove: Click Handler Function
    remove(item) {
      this.items = this.items.filter(v => v !== item);
    }
  }
};

```

{% hint style="info" %}
 Super-powers are granted randomly so please submit an issue if you're not happy with yours.
{% endhint %}

下面是vue 3.0的寫法

    import { value, onMounted } from "vue-function-api";

    export default {
      props: {
        title: String
      },
      setup(props, context) {
        // Reactive value-based variables
        const todo = value("");
        const items = value(["Vue", "is", "Awesome"]);

        // Add: Click Handler Function
        const add = () => {
          if (todo.value) {
            items.value.push(todo.value);
            todo.value = "";
          }
        };

        // Remove: Click Handler Function
        const remove = item => {
          items.value = items.value.filter(v => v !== item);
        };

        // mounted hook
        onMounted( () => {
          console.log(`onMounted ! ${ props.title }`);
        });

        return {
          todo,
          items,
          add,
          remove
        };
      }
    };



