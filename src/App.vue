<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <div @click="모달창열렸니 = false" class="close">X</div>
    </div>
  </div>
  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a>
  </div>
  <div v-for="(a, i) in 원룸들" :key="a">
    <img :src="원룸들[i].image" class="room-img" />
    <h4 @click="모달창열렸니 = true">{{ 원룸들[i].title }}</h4>
    <p>{{ 원룸들[i].price }} 원</p>
    <button @click="신고수[i] += 1">허위매물신고</button>
    <span>신고수 : {{ 신고수[i] }}</span>
  </div>
</template>

<script>
import data from "./assets/oneroom.js";

export default {
  name: "App",
  data() {
    return {
      원룸들: data,
      모달창열렸니: false,
      신고수: [0, 0, 0, 0, 0, 0],
      메뉴들: ["Home", "Shop", "About"],
      products: ["가좌동원룸", "천호동원룸", "마포구원룸"],
    };
  },
  methods: {
    increase() {
      this.신고수 += 1;
    },
  },
  components: {},
};

// <div>
//   <img :src="원룸들[0].image" class="room-img" />
//   <!--HTML속성 안에 넣을 때는 :src 해야함!!-->
//   <h4 @click="모달창열렸니 = true">{{ 원룸들[0].title }}</h4>
//   <p>{{ 원룸들[0].price }} 원</p>
//   <button @click="신고수[0] += 1">허위매물신고</button>
//   <!--신고수 += 1-->
//   <span>신고수 : {{ 신고수[0] }}</span>
// </div>
// <div>
//   <img :src="원룸들[1].image" class="room-img" />
//   <h4 @click="모달창열렸니 = true">{{ 원룸들[1].title }}</h4>
//   <p>{{ 원룸들[1].price }} 원</p>
//   <button @click="신고수[1] += 1">허위매물신고</button>
//   <span>신고수 : {{ 신고수[1] }}</span>
// </div>
// <div>
//   <img :src="원룸들[2].image" class="room-img" />
//   <h4 @click="모달창열렸니 = true">{{ 원룸들[2].title }}</h4>
//   <p>{{ 원룸들[2].price }} 원</p>
//   <button @click="신고수[2] += 1">허위매물신고</button>
//   <span>신고수 : {{ 신고수[2] }}</span>
// </div>
// <div>
//   <img :src="원룸들[3].image" class="room-img" />
//   <h4 @click="모달창열렸니 = true">{{ 원룸들[3].title }}</h4>
//   <p>{{ 원룸들[3].price }} 원</p>
//   <button @click="신고수[3] += 1">허위매물신고</button>
//   <span>신고수 : {{ 신고수[3] }}</span>
// </div>
// <div>
//   <img :src="원룸들[4].image" class="room-img" />
//   <h4 @click="모달창열렸니 = true">{{ 원룸들[4].title }}</h4>
//   <p>{{ 원룸들[4].price }} 원</p>
//   <button @click="신고수[4] += 1">허위매물신고</button>
//   <span>신고수 : {{ 신고수[4] }}</span>
// </div>
// <div>
//   <img :src="원룸들[5].image" class="room-img" />
//   <h4 @click="모달창열렸니 = true">{{ 원룸들[5].title }}</h4>
//   <p>{{ 원룸들[5].price }} 원</p>
//   <button @click="신고수[5] += 1">허위매물신고</button>
//   <span>신고수 : {{ 신고수[5] }}</span>
// </div>
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
.room-img {
  width: 100%;
  margin-top: 40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background-color: darkslateblue;
  padding: 10px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
