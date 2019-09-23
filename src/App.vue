<template>
  <div id="app">
    <HelloWorld />
    <hr />
    <Book />
    <hr />
    <List />
    <hr />
    <Accordion />
    <hr />
    <FlipCard />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import Book from "./components/Book";
import List from "./components/List";
import Accordion from "./components/Accordion";
import FlipCard from "./components/FlipCard";

export default {
  name: "App",
  components: {
    HelloWorld,
    Book,
    List,
    Accordion,
    FlipCard
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
