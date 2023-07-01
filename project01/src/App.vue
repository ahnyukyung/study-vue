<template>
  <header id="header">
    <ul class="menu">
      <li v-for="menu in menus" :key="menu">
        <a href="">{{ menu }}</a>
      </li>
      <!-- <li><a href="">Products</a></li>
      <li><a href="">About</a></li> -->
    </ul>
  </header>

  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <main class="contents">
    <!-- <div v-for="product in products" :key="product">
      <h4 :style="red">{{ product }} 원룸</h4>
      <p>{{ prices[i] }}만원</p>
    </div> -->
    <button @click="increase">허위매물신고</button>
    <span>신고수 : {{ 신고수 }}</span>
    <div>
      <h4>{{ products[0] }} 원룸</h4>
      <p>20만원</p>
      <span>신고수 : {{ 신고수 }}</span>
    </div>
    <div>
      <h4>{{ products[1] }} 원룸</h4>
      <p>30만원</p>
    </div>
    <div>
      <h4>{{ products[2] }} 원룸</h4>
      <p>40만원</p>
    </div>
  </main>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  data() {
    return {
      menus: ["Home", "Products", "About"],
      red: "color : red",
      products: ["염창동", "천호동", "마포구"],
      prices: [10, 20, 30],
      신고수: 0,
    };
  },
  methods: {
    increase() {
      this.신고수++;
    },
  },
  components: {
    // HelloWorld,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#header {
}
#header .menu {
  display: flex;
  justify-content: center;
  list-style: none;
  padding: 30px 0;
  background-color: #2c3e50;
  border-radius: 15px;
}
#header .menu li {
  margin: 0 10px;
}
#header .menu a {
  text-decoration: none;
  color: #fff;
}
</style>
