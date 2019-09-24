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
    <hr />
    <MyAccordion />
    <hr />
    <EmployeeTable v-bind:employees="employees" />
  </div>
</template>

<script>
import HelloWorld from "@/components/HelloWorld";
import Book from "@/components/Book";
import List from "@/components/List";
import Accordion from "@/components/Accordion";
import FlipCard from "@/components/FlipCard";
import MyAccordion from "@/components/MyAccordion";
import EmployeeTable from "@/components/EmployeeTable";

export default {
  name: "App",
  components: {
    HelloWorld,
    Book,
    List,
    Accordion,
    FlipCard,
    MyAccordion,
    EmployeeTable
  },
  data() {
    return {
      employees: [
        {
          id: 1,
          name: "Richard Hendricks",
          email: "richard@piedpiper.com"
        },
        {
          id: 2,
          name: "Bertram Gilfoyle",
          email: "gilfoyle@piedpiper.com"
        },
        {
          id: 3,
          name: "Dinesh Chugtai",
          email: "dinesh@piedpiper.com"
        }
      ]
    };
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
