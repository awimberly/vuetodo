<template>
  <ul>
    <input type="text" class="nes-input" placeholder="Add todo..." v-on:keyup.enter="addTodo" />
    <li v-for="(todo, index) in todos" :key="index" class="flex">
      <label for>
        <input type="checkbox" v-model="todo.done" />
        <span>&nbsp;</span>
      </label>
      <del v-if="todo.done">{{ todo.text }}</del>
      <span v-else>{{ todo.text }}</span>
      <div class="space"></div>
      <button class="nes-btn is-error is-small padding" v-on:click="removeTodo(todo.id)">X</button>
    </li>
  </ul>
</template>
<script>
export default {
  name: "Todo",
  data() {
    return {
      todos: [
        { text: "Call Luigi", done: false, id: Date.now() },
        {
          text: "Pick up Tanooki suit from cleaners",
          done: false,
          id: Date.now() + 1
        },
        {
          text: "Ask Toad to return Frog suit",
          done: false,
          id: Date.now() + 2
        },
        {
          text:
            "Actually have a man-to-lizard conversation with Bowser. This kidnapping the princess for over 25 years is ridiculous. He must have smashed.",
          done: false,
          id: Date.now() + 3
        }
      ]
    };
  },
  methods: {
    addTodo(event) {
      const text = event.target.value;
      this.todos.push({ text, done: false, id: Date.now() });
      event.target.value = "";
    },
    removeTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
};
</script>