<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
      {{logo}} <!--자주 변경되지 않는 데이터들은 Binding 할 일이 없다.-->
      <h4 class="red" :style="스타일">{{products[0]}}</h4> <!--속성에는 {{}} 대신 속성 앞에 :(콜론) 붙여주면 적용이 된다.-->
      <p>{{ price1 }} 만원</p>
  </div>
  <div>
      <h4>{{products[1]}}</h4>
      <p>{{ price2 }} 만원</p> <!-- {{}} 중괄호 2개에 data()안에있는 변수명을 적어주기만 하면된다.-->
  </div>
  <div>
      <h4>{{products[2]}}</h4>
      <p>{{ price3 }} 만원</p> <!-- {{}} 중괄호 2개에 data()안에있는 변수명을 적어주기만 하면된다.-->
  </div>
</template>

<script>



/*
  [ Vanila javascript ]
  document.getElementById().innerHTML = ??
*/

/* 
  [ Data binding 하는 이유 ]
  하드코딩 해 놓으면 가변적인 데이터를 저장해두기 어려움 (실시간 자동 렌더링기능)
  webapp을 만들수있음
*/
export default {
  name: 'App',
  data() { // data(){return{}} 안이 data 통 과 같음 여기에 vue 코드를 모두 짜면 된다.
    return {
      price1 : 80, // key : value 형태로 저장해주면 된다. (변수 : 값할당)
      price2 : 70,
      price3 : 65,
      logo : '원룸샵',
      스타일 : 'color : blue',
      products : ['역삼동원룸', '천호동원룸', '마포구원룸']
    }
  },
  components: {
  }
}
</script>

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
