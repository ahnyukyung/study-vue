<template>
  <div class="modal_wrap" v-if="모달창 === true">
    <button class="btn_close" @click="모달창 = false">닫기</button>
    <div class="modal">
      <h4>상세 페이지</h4>
      <p>내용</p>
    </div>
  </div>

  <header id="header">
    <ul class="menu">
      <li v-for="menu in menus" :key="menu">
        <a href>{{ menu }}</a>
      </li>
      <!-- <li><a href="">Products</a></li>
      <li><a href="">About</a></li>-->
    </ul>
  </header>
  <main class="contents">
    <!-- <div v-for="product in products" :key="product">
      <h4 :style="red">{{ product }} 원룸</h4>
      <p>{{ prices[i] }}만원</p>
    </div>-->
    <!-- <span v-for="i in 10" :key="{ i }">{i}</span> -->
    <section v-for="(oneroom, idx) in onerooms" :key="{ idx }" class="item_box">
      <img :src="oneroom.image" alt="" />
      <h4>{{ oneroom.title }} 원룸</h4>
      <article>{{ oneroom.content }} 원룸</article>
      <p>{{ oneroom.price }}만원</p>
      <button @click="open">자세히보기</button>
      <!-- <div class="btn_wrap">
        <button @click="신고수[0]++">허위매물신고</button>
        <span>신고수 : {{ 신고수[0] }}</span>
      </div> -->
    </section>

    <!-- <section class="item_box">
      <h4>{{ products[1] }} 원룸</h4>
      <p>30만원</p>
      <div class="btn_wrap">
        <button @click="increase">허위매물신고</button>
        <span>신고수 : {{ 신고수[1] }}</span>
      </div>
    </section> -->

    <!-- <section class="item_box">
      <h4>{{ products[1]  }} 원룸</h4>
      <p>40만원</p>
      <div class="btn_wrap">
        <button @click="increase">허위매물신고</button>
        <span>신고수 : {{ 신고수[2] }}</span>
      </div>
    </section> -->
  </main>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import onerooms from "./assets/oneroom";

export default {
  name: "App",
  data() {
    return {
      menus: ["Home", "Products", "About"],
      red: "color : red",
      신고수: [0, 0, 0],
      모달창: false,
      onerooms: onerooms,
    };
  },
  methods: {
    increase() {
      this.신고수++;
    },
    open() {
      this.모달창 = true;
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
.modal_wrap {
  position: absolute;
  left: 50%;
  top: 50px;
  width: 80%;
  min-height: 200px;
  background-color: #df6565;
  border-radius: 20px;
  transform: translateX(-50%);
}
.modal_wrap .btn_close {
  position: absolute;
  top: 0;
  right: 0;
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
section {
  margin-bottom: 20px;
}
.item_box img {
  width: 100%;
  max-width: 800px;
}
</style>
