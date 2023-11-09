<template>

<div class="black-bg" v-if="모달창열렸니 == true">  <!-- v-if 안에 조건이 참일때면 모달창을 보여줌-->
  <div class="white-bg">
    <h4>상세페이지임</h4>
    <P>상세페이지 내용임</P>
    <button @click="모달창열렸니 = false">모달창 닫기</button>
  </div>

</div>



<div class="menu">
    <!-- 
    일반 사용

  <a>Home</a>
  <a>Product</a>
  <a>About</a>
  -->

  <a v-for="작명 in 메뉴들" :key="작명">{{작명}}</a>

  <!-- 반복문 사용
    <a v-for="(a, i) in 메뉴들" :key="i">{{작명}}</a>
  -->

</div>
  <h1>원룸샾</h1>
  <div>
    <img src="./assets/room0.jpg" class="room-img">
    <h4 @click="모달창열렸니 = true">{{ products[0] }} </h4>
    <p>{{ prices[0] }} 만원</p>
    <button @click="신고수[0]++">허위매물신고</button> 
    <span>신고 수 : {{ 신고수[0] }}</span>
    <!-- 혹은 v-on:click
            <button @click="신고수 += 1">허위매물신고</button> <span>신고 수 : {{ 신고수 }}</span>
            <button @mouseover="신고수 += 1">허위매물신고</button> <span>신고 수 : {{ 신고수 }}</span>

            ** 함수를 자바스크립트에서 사용하는 이유는 긴 문장을 짧게 쓰고 싶을때
            function 어쩌구() {
              console.log('강명석')
              console.log('강명석')
              console.log('강명석')
            }

            어쩌구() 하면 위 긴 코드가 한번에 다 실행됨
    
    -->    
  </div>


  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4>{{ products[1] }} </h4>
    <p>{{ prices[1] }} 만원</p>
    <button @click="신고수[1]++">허위매물신고</button> 
    <span>신고 수 : {{ 신고수[1] }}</span>
  </div>

  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4>{{ products[2] }} </h4>
    <p>{{ prices[2] }} 만원</p>
    <button @click="신고수[2]++">허위매물신고</button> 
    <span>신고 수 : {{ 신고수[2] }}</span>
  </div>


</template>

<script>

export default {
  name: 'App',
  data(){
    return {    // 데이터 저장공간을 vue에서 state라고 한다 - 상태(UI  상태를 저장할수 있음)
      // price1 : 80, //실시간 자동 렌더링 쓰려면 // 웹/앱 변동될때 부드럽게 변동 전환
      // price2 : 70, // 속성은 :, 변수 {{ }}
      // price3 : 90,
      prices : [70, 80, 90],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      신고수 : [0, 0, 0],
      메뉴들 : ['Home', 'Shop', 'About'],


      // 5강 동적 UI  만드는 법
      //0. html로 UI를 디자인 해두고 CSS까지 넣어둠 => 2가지 스탭으로 진행
      //1. ui의 현재 상태를 데이터로 저장해둠(열렸니 true/false)
      모달창열렸니 : false, 
      //2. 데이터에 따라 UI가 어떻게 보일지 작성( v-if 로 조작)
      // false 일때는 안보임, true 일때는 보임


    }
  },

  methods : { // 함수를 만드는 공간
    // increase() {
    //   this.신고수 += 1;
    // }

    함수2() {

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
  margin-top: 10px;
}

.menu {
  background: darkslateblue;
  padding : 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;

}

body {
  margin : 0
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; 
  height: 100%;
  background: rgba(0,0,0,0.5);
  position:fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding:20px;
}
.room-img {

  width: 100%;
  margin-top: 40px;
}

</style>
