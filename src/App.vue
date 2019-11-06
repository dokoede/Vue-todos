<template>
  <div id="app" class="container">
    <img alt="Vue logo" src="./assets/logo.png" />
    <Header msg="Welcome to Your Vue-Todo App" />
    <todolist />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Todolist from "./components/Todolist";
export default {
  name: "app",
  components: {
    Header,
    Todolist
  }
};
</script>

<style>
.container {
  max-width: 900px;

  margin: 10px auto;
}
#app {
  font-family: "raleway", "Avenir", Helvetica, Arial, sans-serif;
  display: flex;
  flex-direction: column;
  align-items: center;
  border: 1px solid gray;
  padding: 20px;
}
img {
  width: 50px;
}
</style>
