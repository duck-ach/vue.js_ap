<!--HTML-->
<template>
  <img alt="Vue logo" src="./assets/logo.png">
  원룸샵 <!-- 값이 바뀌지 않는 것은 굳이 데이터바인딩 하지 않아도 됨. -->
  <div class="menu">
    <a v-for="(menu, i) in menus" :key="i">{{menu}}</a>
    <!--Vue 반복문 특 변수 작명 2개까지 가능 왼쪽변수:array 내 데이터, 오른쪽변수:1씩 증가하는 정수-->
  </div>

  <div v-for="(product, i) in products" :key="i">
      <h4>{{product}}</h4>
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
</style>
