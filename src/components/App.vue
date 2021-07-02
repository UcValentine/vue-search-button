<template>
  <div id="app">
  <div class="search-wrapper">
    <input type="text" v-model="search" placeholder="Search">
  </div>
    <div class="wrapper">
      <div class="card" v-for="post in filteredPosts" :key="post.id">
      <post :post="post"></post>
    </div>
    </div>
  </div>
</template>

<script>
import Post from "./Post";

export default {
  name: "App",
  components: {
    Post
  },
  data() {
    return {
      search: "",
      posts: [
        {
          id: 1,
          title: "VueJs",
          body: "Vue.js features an incrementally adaptable architecture that focuses on declarative rendering and component composition. The core library is focused on the view layer only",
          img: "https://vuejs.org//images/logo.png"
        },
        {
          id: 2,
          title: "Movies",
          body: "Don Cheadle and Benicio Del Toro star in Steven Soderbergh’s new film, This Movies is a Detroit-set period thriller with a lot on its mind.",
          img: "https://upload.wikimedia.org/wikipedia/en/thumb/d/db/The_Movies_Coverart.jpg/220px-The_Movies_Coverart.jpg"
        },
        {
          id: 3,
          title: "Sports",
          body: "Our Sports News Today; The Bucks were missing star player Giannis Antetokounmpo because of a knee injury but four of their five starters scored at least 22 points.",
          img: "https://www.chinadaily.com.cn/photo/images/attachement/jpg/site1/20171115/d8cb8a5155b01b75fdbf27.jpg"
        }
      ]
    };
  },
  computed: {
    filteredPosts() {
      return this.posts.filter(post =>
        post.body.toLowerCase().includes(this.search.toLowerCase())
      );
    }
  }
};
</script>

<style>
 div#app {
	 display: flex;
	 align-items: center;
	 justify-content: center;
	 flex-direction: column;
   text-align: center;
}
 div#app .search-wrapper {
	 position: relative;
   margin-top: 10px;
}
 div#app .search-wrapper label {
	 position: absolute;
	 font-size: 12px;
	 color: rgba(0, 0, 0, .50);
	 top: 8px;
	 left: 12px;
	 z-index: -1;
	 transition: 0.15s all ease-in-out;
}
 div#app .search-wrapper input {
	 padding: 4px 12px;
	 color: rgba(0, 0, 0, .70);
	 border: 1px solid rgba(0, 0, 0, .12);
	 transition: 0.15s all ease-in-out;
	 background: white;
}
 div#app .wrapper {
	 display: flex;
	 max-width: 944px;
	 flex-wrap: wrap;
	 padding-top: 12px;
}
 div#app .card {
	 box-shadow: rgba(0, 0, 0, 0.117647) 0px 1px 6px, rgba(0, 0, 0, 0.117647) 0px 1px 4px;
	 max-width: 224px;
	 margin: 10px;
   padding: 10px;
	 transition: 0.15s all ease-in-out;
}
 div#app .card:hover {
	 transform: scale(1.1);
}
 div#app .card img {
	 height: 100px;
   width: 100px;
   align-items: center;
}
</style>
