<template>
  <div class="hello">
    <h1>{{ msg + " " + name}}</h1>
    <h2>Essential Links</h2>
    <img :src="img.src" :alt="img.alt" />
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
      name: "Josefine",
      img: {
        src: "https://placeimg.com/200/200/animals",
        alt: "Image of some animal"
      }
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
