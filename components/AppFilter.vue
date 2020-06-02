<template>
  <div id="app">
    <div class="portfolio-wrapper">
      <div class="panel-item">
        <a v-on:click="filterTag('all')">
          <span class="item">All</span>
        </a>
        <a v-on:click="filterTag('tag1')">
          <span class="item">Website</span>
        </a>
        <a v-on:click="filterTag('tag2')">
          <span class="item">Games</span>
        </a>
        <a v-on:click="filterTag('tag3')">
          <span class="item">Design</span>
        </a>
      </div>
      <transition-group name="grid-container" class="grid-container" tag="section">
        <div class="content" v-for="content in filteredContents" v-bind:key="content.id">
          <a v-bind:href="content.link" target="_blank">
            <figure class="card-image">
              <img v-bind:src="content.img" v-bind:alt="content.title" />
              <figcaption>
                <h2 class="titlecard">
                  <span class="card-title">{{ content.title }}</span>
                </h2>
                <p class="card-content">{{ content.desc }}</p>
              </figcaption>
            </figure>
          </a>
        </div>
      </transition-group>
    </div>
  </div>
</template>

<script>
import lodash from "lodash";
// import image1 from "/img/8.jpg";
// import image2 from "/img/9.jpg";

export default {
  name: "app-filter",
  data() {
    return {
      search_filter: "",
      currentTag: "all",
      contents: [
        {
          id: 0,
          img: "/img/8.jpg",
          title: "Les histoires dans le développement des enfants",
          desc:
            "la lecture d’histoires a une influence considérable sur la compréhension qu’ont les enfants du monde",
          link: "",
          tags: ["all", "tag1"]
        },
        {
          id: 1,
          img: "/img/8.jpg",
          title: "lorem ipsum seit ralentur",
          desc:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam eu malesuada libero super gingle no dolorem",
          link: "",
          tags: ["all", "tag2"]
        },
        {
          id: 2,
          img: "http://placehold.it/320x213",
          title: "lorem ipsum seit ralentur",
          desc:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam eu malesuada libero",
          link: "",
          tags: ["all", "tag3"]
        },
        {
          id: 3,
          img: "http://placehold.it/320x213",
          title: "lorem ipsum seit ralentur",
          desc:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam eu malesuada libero",
          link: "",
          tags: ["all", "tag1"]
        },
        {
          id: 4,
          img: "http://placehold.it/320x213",
          title: "lorem ipsum seit ralentur",
          desc:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam eu malesuada libero",
          link: "",
          tags: ["all", "tag2"]
        },
        {
          id: 5,
          img: "http://placehold.it/320x213",
          title: "lorem ipsum seit ralentur",
          desc:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam eu malesuada libero",
          link: "",
          tags: ["all", "tag3"]
        },
        {
          id: 6,
          img: "http://placehold.it/320x213",
          title: "lorem ipsum seit ralentur",
          desc:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam eu malesuada libero",
          link: "",
          tags: ["all", "tag1"]
        },
        {
          id: 7,
          img: "http://placehold.it/320x213",
          title: "lorem ipsum seit ralentur",
          desc:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam eu malesuada libero",
          link: "",
          tags: ["all", "tag2"]
        },
        {
          id: 8,
          img: "http://placehold.it/320x213",
          title: "lorem ipsum seit ralentur",
          desc:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam eu malesuada libero",
          link: "",
          tags: ["all", "tag3"]
        }
      ]
    };
  },
  computed: {
    filteredContents: function() {
      let tempTag = this.currentTag;
      return this.contents
        .filter(function(item) {
          return item.tags.indexOf(tempTag) !== -1;
        })
        .filter(item => {
          return item.title.match(this.search_filter);
        });
    }
  },
  methods: {
    filterTag: function(tag) {
      this.currentTag = tag;
    },
    shuffleTag: function() {
      this.contents = _.shuffle(this.contents);
    }
  }
};
</script>

<style>
html,
body {
  background-color: #f9f9f9;
  height: 100%;
  width: 100%;
}
[v-cloak] {
  display: none;
}
.panel-item {
  position: relative;
  text-align: center;
  margin: 10px 0px 10px 0px;
}
.panel-item > a {
  display: inline-flex;
  padding: 18px 20px;
  text-decoration: none;
  font-size: 20px;
}
.panel-item > a:hover {
  color: var(--font);
}
.item {
  position: relative;
  cursor: pointer;
}
.item::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 2px;
  bottom: 0;
  left: 0;
  transform: scaleX(0);
  transform-origin: bottom;
  transition: transform 0.25s ease-out;
}
.item:hover::after {
  background-color: var(--font);
  transform: scaleX(1);
  transform-origin: bottom center;
}
.grid-container {
  display: grid;
  grid-gap: 2em;
  grid-template-columns: repeat(auto-fit, minmax(auto, 320px));
  grid-auto-rows: 1fr;
  justify-content: center;
  grid-auto-flow: dense;
}
.grid-container-enter-active,
.grid-container-leave-active {
  transition: all 1s ease;
}
.grid-container-enter,
.grid-container-leave-to {
  opacity: 0;
}
.content {
  width: 320px;
  transition: all 0.8s ease;
}
.content > a {
  text-decoration: none;
  color: #888;
  cursor: pointer;
}

/* Common style */
.card-image {
  position: relative;
  float: left;
  overflow: hidden;
  margin: 0;
  min-width: 320px;
  max-width: 480px;
  max-height: 360px;
  width: 48%;
  height: auto;
  background: #3085a3;
  text-align: center;
  cursor: pointer;
  font-family: "Nunito", sans-serif;
}

.card-image img {
  position: relative;
  display: block;
  min-height: 100%;
  max-width: 100%;
  opacity: 0.7;
}

.card-image figcaption {
  color: #fff;
  text-transform: uppercase;
  font-size: 1.25em;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.card-image figcaption::before,
.card-imagefigcaption::after {
  pointer-events: none;
}

.card-image figcaption,
.card-image figcaption > a {
  position: absolute;
  top: 0;
  left: 0;
}

/* Anchor will cover the whole item by default */
/* For some effects it will show as a button */
.card-image figcaption > a {
  z-index: 1000;
  text-indent: 200%;
  white-space: nowrap;
  font-size: 0;
  opacity: 0;
}

.card-image h2 {
  font-weight: 300;
  line-height: 1;
}

.card-image h2 span {
  font-weight: 800;
  font-size: 1.3rem;
  line-height: 1.15;
}

.card-image h2,
.card-image p {
  margin: 0;
}

.card-image p {
  letter-spacing: 1px;
  font-size: 68.5%;
}

/* Individual effects */

.card-image {
  background: #030c17;
}

.card-image img {
  opacity: 0.7;
  -webkit-transition: opacity 0.35s;
  transition: opacity 0.35s;
}

.card-image figcaption::before {
  position: absolute;
  top: 20px;
  right: 30px;
  bottom: 30px;
  left: 30px;
  border: 2px solid #fff;
  box-shadow: 0 0 0 30px rgba(255, 255, 255, 0.2);
  content: "";
  opacity: 0;
  -webkit-transition: opacity 0.35s, -webkit-transform 0.35s;
  transition: opacity 0.35s, transform 0.35s;
  -webkit-transform: scale3d(1.4, 1.4, 1);
  transform: scale3d(1.4, 1.4, 1);
}

.card-image h2 {
  margin: 10% 10% 0;
  -webkit-transition: -webkit-transform 0.35s;
  transition: transform 0.35s;
  letter-spacing: 2px;
}

.card-image p {
  padding: 0.5rem 2rem 2rem 2rem;
  line-height: 1.5;
  opacity: 0;
  -webkit-transition: opacity 0.35s, -webkit-transform 0.35s;
  transition: opacity 0.35s, transform 0.35s;
  -webkit-transform: scale(1.5);
  transform: scale(1.5);
  margin: 0 1rem 1rem 1rem;
  font-size: 0.75rem;
  font-weight: 500;
}

.card-image:hover h2 {
  -webkit-transform: scale(0.9);
  transform: scale(0.9);
}

.card-image:hover figcaption::before,
.card-image:hover p {
  opacity: 1;
  -webkit-transform: scale3d(1, 1, 1);
  transform: scale3d(1, 1, 1);
}

.card-image:hover figcaption {
  background-color: rgba(58, 52, 42, 0);
}

.card-image:hover img {
  opacity: 0.35;
}

/* Media queries */
@media screen and (max-width: 50em) {
  .card-image {
    display: inline-block;
    float: none;
    margin: 3% auto;
    width: 100%;
  }
}
</style>