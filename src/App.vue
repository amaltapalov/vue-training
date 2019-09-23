<template>
  <div id="app">
    <HelloWorld />
    <hr />
    <Book />
    <hr />
    <List />
    <hr />
    <Accordion />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import Book from "./components/Book";
import List from "./components/List";
import Accordion from "./components/Accordion";

export default {
  name: "App",
  components: {
    HelloWorld,
    Book,
    List,
    Accordion
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
