<template>
  <div class="book">
    <h2 v-on:click="toggleDetails">{{ title }}</h2>
    <div id="bookDetail" v-show="showDetail">
      <p>{{ author }}</p>
      <p>{{ summary }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Book",
  data() {
    return {
      title: "The Sirens of Titans",
      author: "Kurt Vonnegut",
      summary: "This is a summary of Sirens of Titans",
      showDetail: false
    };
  },
  methods: {
    toggleDetails: function() {
      this.showDetail = !this.showDetail;
    }
  }
};
</script>
