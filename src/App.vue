<template>
  <div id="app">
    <h1>Mario's TO Do List:</h1>
    <Todo></Todo>
    <i class="nes-mario"></i>
  </div>
</template>

<script>
import Todo from "./components/todo.vue";

export default {
  name: "app",
  components: {
    Todo
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Press+Start+2p");
@import url("https://unpkg.com/nes.css/css/nes.css");

html,
body,
pre,
code,
kbd,
samp {
  font-family: "Press Start 2P";
}

body {
  background: #20262e;
  padding: 20px;
}

#app {
  background: #fff;
  border-radius: 4px;
  padding: 20px;
  transition: all 0.2s;
}

li {
  margin: 8px 0;
}

del {
  color: rgba(0, 0, 0, 0.3);
}

.padding {
  padding: 1px 7px 2px;
}

.flex {
  display: flex;
}

.space {
  flex-grow: 1;
}
</style>