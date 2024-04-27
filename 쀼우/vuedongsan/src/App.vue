<!--HTML-->
<template>
  <img alt="Vue logo" src="./assets/logo.png">
  원룸샵 <!-- 값이 바뀌지 않는 것은 굳이 데이터바인딩 하지 않아도 됨. -->
  <div>
      <!--속성을 데이터바인딩 하려면 앞에 :(콜론) 을 붙여주면 된다.-->
      <!-- <h4 v-for="product in products" :key="product[0]">{{product}}</h4> -->
      <h4>{{products[0]}}</h4>
      <p>{{price1}} 만원</p>
  </div>
  <div>
      <h4>{{products[1]}}</h4>
      <p>{{price2}} 만원</p>
  </div>
    <div>
      <h4>{{products[2]}}</h4>
      <p>{{price3}} 만원</p>
  </div>
</template>

<!--JS-->
<script>


export default {
  name: 'App',
  data() {
    return {
      // object 자료형식 모든 데이터 넣을 수 있음. ex) 변수
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      price1 : 60,
      price2 : 80, 
      price3 : 70,
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
</style>
