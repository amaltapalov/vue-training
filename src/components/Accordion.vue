<template>
  <div class="container">
    <div id="media-list">
      <h1>{{ title }}</h1>
      <select v-on:change="filterList">
        <option value=" ">Select a type of media...</option>
        <option v-for="item in uniqueItemList" v-bind:key="item">{{item}}</option>
      </select>
      <ul>
        <!-- setting List item from Array -->
        <li
          v-show="type === '' || type === media.type"
          v-for="media in mediaList"
          v-on:click="toggleDetails(media)"
          v-bind:key="media.title"
          v-bind:class="[media.showDetail ? 'less' : 'more', media.type.split(' ').join('-').toLowerCase()]"
        >
          <h3>{{media.title}}</h3>
          <div v-show="media.showDetail">
            <p>{{media.description}}</p>
            <p class="byline" v-if="media.contributor">By: {{media.contributor}}</p>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Accordion",
  data() {
    return {
      title: "Treehouse Public Library",
      mediaList: media,
      type: ""
    };
  },
  methods: {
    //   I added 'media' to refer to exact list item
    toggleDetails: function(media) {
      media.showDetail = !media.showDetail;
    },
    filterList: function() {
      this.type = event.target.value;
    }
  },
  computed: {
    uniqueItemList: function() {
      const types = [];
      this.mediaList.forEach(item => {
        if (!types.includes(item.type)) {
          types.push(item.type);
        }
      });
      return types;
    }
  }
};

const media = [
  {
    title: "Hop on Pop",
    description: "A delightful children's book.",
    type: "book",
    contributor: "Dr. Suess",
    showDetail: false
  },
  {
    title: "The Joy of Painting",
    description: "Create a world of happy little trees!",
    type: "DVD",
    contributor: "Bob Ross",
    showDetail: false
  },
  {
    title: "Supernatural: The Complete 12th Season",
    description: "A (literally) neverending roadtrip.",
    type: "DVD",
    contributor: "",
    showDetail: false
  },
  {
    title: "Planet Earth II",
    description: "Hours of beautiful but heart attack-inducing nature footage",
    type: "streaming video",
    contributor: "David Attenborough",
    showDetail: false
  },
  {
    title: "Titanic",
    description: "The boat sinks.",
    type: "DVD",
    contributor: "James Cameron",
    showDetail: false
  },
  {
    title: "The Sirens of Titan",
    description:
      "Mankind flung its advance agents ever outward, ever outward... it flung them like stones.",
    type: "book",
    contributor: "Kurt Vonnegut",
    showDetail: false
  },
  {
    title: "Better Call Saul",
    description: "A slow-burning Breaking Bad prequel.",
    type: "streaming video",
    contributor: "",
    showDetail: false
  }
];
</script>

<style scoped>
body {
  font-family: "Open Sans", sans-serif;
  background: #f4f4f4;
}

.container {
  max-width: 80%;
  margin: auto;
  min-height: initial;
  position: relative;
}

.container > div {
  padding-bottom: 30px;
}

h3 {
  cursor: pointer;
  display: inline;
}

p {
  color: #333;
}

.more:after {
  content: "\25BC";
  font-size: 8px;
  position: absolute;
  right: 20px;
  top: 50%;
  margin-top: -10px;
  font-size: 16px;
  color: #333;
}

.less:after {
  content: "\25B2";
  font-size: 8px;
  position: absolute;
  right: 20px;
  top: 50%;
  margin-top: -10px;
  font-size: 16px;
  color: #333;
}

ul {
  list-style-type: none;
  padding-left: 0;
  border-radius: 5px;
}

li {
  border: #eaeaea solid 1px;
  margin: 10px 0;
  padding: 15px;
  border-left: #95effe solid 5px;
  position: relative;
  background: #fff;
  -webkit-box-shadow: 0 1px 2px rgba(0, 0, 0, 0.07);
  -moz-box-shadow: 0 1px 2px rgba(0, 0, 0, 0.07);
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.07);
}

li.book {
  border-left: #eb727e solid 5px;
}

li.streaming {
  border-left: #a0f2d0 solid 5px;
}

.byline {
  font-size: 14px;
  font-style: italic;
}

select {
  position: absolute;
  right: 0;
  top: 5px;
  -webkit-appearance: button;
  -webkit-border-radius: 2px;
  -webkit-box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.1);
  -webkit-padding-end: 20px;
  -webkit-padding-start: 2px;
  -webkit-user-select: none;
  background-image: url(../assets/arrow.png),
    -webkit-linear-gradient(#fff, #fff 40%, #fff);
  background-position: 97% center;
  background-repeat: no-repeat;
  border: 1px solid #eaeaea;
  color: #555;
  font-size: inherit;
  overflow: hidden;
  padding: 5px 10px;
  text-overflow: ellipsis;
  white-space: nowrap;
  width: 300px;
  outline: none;
}
</style>