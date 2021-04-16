<template>
  <!-- 반복문 만들기
  <태그 v-for = "(이름, i) in 횟수">
  반복문 쓸 때는 꼭 key를 함께 써줘야한다 >> 
  :key="i"
  -->
  <div class="menu">
    <!-- <a v-for="name in 3" :key="name" href="#">Home</a> -->
    <a v-for="(name, i) in menues" :key="i" href="#"> {{ name }}</a>
  </div>

  <div class="info_container">
    <!-- 데이터바인딩 
  1) 태그 안의 값을 데이터 바인딩 할 때 >> 중괄호 2개( {{}} )
  2) 태그 내 속성을 데이터 바인딩 할 떄 >> :속성="데이터이름" (속성 앞에 콜론 붙여주기) -->
    <div class="info" v-for="(name, i) in products" :key="i">
      <h4 :style="style">{{ products[i] }} 원룸</h4>
      <p>{{ price[i] }} 만원</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      // 데이터 보관함(object형식)
      price: [60, 80, 100, 500, 900],
      style: "color: darkblue",
      products: ["역삼동", "천호동", "마포구", "종로구", "아현동", "길음동"],
      menues: ["Home", "Shop", "About"],
    };
  },
  components: {},
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
.menu {
  background: darkslateblue;
  padding: 30px;
  border-radius: 5px;
  font-size: 30px;
}
.menu a {
  color: #fff;
  padding: 20px;
  text-decoration: none;
}
.info_container {
  display: flex;
  justify-content: center;
  max-width: 80vw;
  margin: 0 auto;
  overflow: auto;
}

.info {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  width: 300px;
  height: 300px;
  margin: 15px;
  border: 1px solid #000;
  border-radius: 10px;
}

.info h4,
.info p {
  font-size: 25px;
}
</style>
