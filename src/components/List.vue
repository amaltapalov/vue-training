
<template>
  <div>
    <ul>
      <li
        v-bind:style="{color: item}"
        v-for="(item, index) in rainbow"
        v-bind:key="index"
      >{{index}} - {{ item }}</li>
    </ul>
  </div>
</template>

<script>
const colorsOfTheRainbow = [
  "red",
  "orange",
  "yellow",
  "green",
  "blue",
  "indigo",
  "violet"
];

export default {
  name: "List",
  data() {
    return {
      rainbow: colorsOfTheRainbow
    };
  }
};
</script>

