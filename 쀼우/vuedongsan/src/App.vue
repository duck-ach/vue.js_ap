<!--HTML-->
<template>
  <img alt="Vue logo" src="./assets/logo.png">
  원룸샵 <!-- 값이 바뀌지 않는 것은 굳이 데이터바인딩 하지 않아도 됨. -->
  <div class="menu">
    <a v-for="(menu, i) in menus" :key="i">{{menu}}</a>
    <!--Vue 반복문 특 변수 작명 2개까지 가능 왼쪽변수:array 내 데이터, 오른쪽변수:1씩 증가하는 정수-->
  </div>


  <div v-for="(product, i) in products" :key="i" class="section">
    <!-- v-if="조건식" -->
      <div class="black-bg" v-if="모달창열렸니[i] == true">
        <div class="white-bg">
          <h4>{{product}} 상세페이지임</h4>
          <p>{{prices[i]}} 만원임</p><br/>
          <button @click="모달창열렸니[i] = false">닫기</button>
        </div>
      </div>

      <img :src=images[i] class="profile_img">
      <h4 @click="모달창열렸니[i] = true">{{product}}</h4>
      <p>{{prices[i]}} 만원</p>
      <!-- v-on:click="자바스크립트" -->
      <button @click="신고수s[i] += 1">허위매물신고</button> <span>신고수 : {{신고수s[i]}}</span>
  </div>
</template>

<!--JS-->
<script>

export default {
  name: 'App',
  data() {
    return {
      모달창열렸니 : [false, false, false],
      images : ['	http://localhost:8080/img/dog.d475cc24.jpg', "http://localhost:8080/img/IMG_5536.4ad8e957.jpg", "	http://localhost:8080/img/IMG_6049.7849fcd9.jpg"],
      신고수s : [0, 0, 0],
      // object 자료형식 모든 데이터 넣을 수 있음. ex) 변수
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      menus : ['Home', 'Shop', 'About'],
      prices : [60, 70, 80],
    }
  },
  methods : {
    increase() {
      // this.신고수 += 1
    }
  },
  components: {
    
  }
}
</script>

<!--CSS-->
<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
  left: 0%;
  top: 0%;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
  margin-top: 200px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}

.section {
  padding: 30px;
}

.profile_img {
  width: 100px;
  height: 100px;
}
</style>
