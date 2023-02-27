<template>
<!-- run : npm run serve -->
  <!-- Vue를 이용했을 때 장점 : HTML도 반복문으로 쓸수있다. -->
  <div class="menu">
    <!--
      <태그 v-for="작명 in 반복횟수" :key="작명">
    -->
    <a v-for="home in menu" :key="home">{{home}}</a>

    <!--
      data() 안에 요소를 넣어놓으면 v-for문에서 그 요소의 개수만큼 반복문을 돌릴수있다.
      작명한 변수는 데이터 안의 자료가 된다.

      - key의 용도는 반복문 돌린 요소를 컴퓨터가 구분하기 위해서 사용한다.
      - in 왼쪽에 작명을 2개까지 할 수 있다. ex (home, police)
    -->
  </div>

    <div class="menu">
    <a v-for="(a,i) in 5" :key="i">{{i}}</a>

    <!--
      - in 왼쪽에 작명을 2개까지 할 수 있다. ex (home, police)
    -->
  </div>
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
<!--반복문 과제-->
<h3>반복문과제</h3> <!--아래 변수를 2개 넣으면 배열처럼 0,1,2 이렇게 할 수 있다. -->
<div v-for="(products,prices) in products" :key="products">
  <div>
      {{logo}} <!--자주 변경되지 않는 데이터들은 Binding 할 일이 없다.-->
      <h4 class="red" :style="스타일">{{products}}</h4> <!--속성에는 {{}} 대신 속성 앞에 :(콜론) 붙여주면 적용이 된다.-->
      <p>{{prices}} 만원</p>
  </div>
</div>


<!--이벤트 핸들러로 허위매물 버튼 만들기-->
<h3>허위매물버튼</h3>
<div>
    <h4>{{products[0]}}</h4> <!--Vanila js에서는 버튼누르면 숫자찾아서 +1, 그리고 그걸 HTML에 반영 -->
    <p>50만원</p> <!-- click 이벤트에 사용하는 것 v-on: = @ --> <!--신고수를 Data Binding--> <!-- vue는 실시간 렌더링이되므로..! -->
    <button @click="신고수[0]++">허위매물신고</button> <span>신고수 : {{신고수[0]}}</span>
</div> <!-- '신고수++' 대신 '+=신고수' 사용해도 됨 --> <!-- @mouseover, @drag, @input(input Tag일때), ... 등등 다양한 이벤트가 있음 -->
<div>
    <h4>{{products[1]}}</h4>
    <p>60만원</p> <!-- vue에서는 함수를 호출할 때 ()를 붙이지 않는다. -->
    <button @click="신고수[1]++">허위매물신고</button> <span>신고수 : {{신고수[1]}}</span>
</div>
<div>
    <h4>{{products[2]}}</h4>
    <p>70만원</p>
    <button @click="신고수[2]++">허위매물신고</button> <span>신고수 : {{신고수[2]}}</span>
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
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      prices : [80, 50, 60],
      menu : ['Home', 'Shop', 'About'],
      신고수 : [0, 0, 0],
    }
  },
  // js에서 함수쓰는 이유 : 코드가 길고 복잡한 것을 함수안에 담아서 짧은 단어 하나로 축약시켜주는 것
  // vue에서 함수 만드는 공간이 정해져있음.
  methods : {
    increase() {
      this.신고수 += 1
    } // js내에서 사용하고싶으면 this.을 꼭 붙여줘야함 (js Object를 뜻하기 때문)
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
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding:10px;
}

</style>
