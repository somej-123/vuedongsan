<template>

<div class="black-bg" v-if="모달창열렸니 == true">
  <div class="white-bg">
    <h4>상세페이지임</h4>
    <p>상세페이지 내용임</p>
    <button @click="모달창열렸니=false">닫기</button>
  </div>
</div>


  <div class="menu">
    <a v-for="(작명) in 메뉴들" :key="작명">{{ 작명 }}</a>
  </div>



  <div v-for="oneRoomList in 원룸들" :key="oneRoomList.title">
    <img :src="oneRoomList.image" class="room-img"/>
    <h4 @click="모달창열렸니 = true">{{ oneRoomList.title }}</h4>
    <p>{{ oneRoomList.price }}원</p>
    <button @click="신고수[0]++">허위매물신고버튼</button> <span>신고수 : {{ 신고수[0] }}</span>
  </div>
</template>

<script>

import data from './assets/oneroom.js';

export default {
  name: 'App',
  //데이터 보관함
  data(){
    return {
      원룸들 : data,
      모달창열렸니 : false,
      신고수 : [0,0,0],
      메뉴들 : ['Home', 'Shop', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸']
    }
  },
  methods : {
  },

  components: {
  }
}
</script>

<style>
body{
  margin: 0;
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background: darkslateblue;
  padding:15px;
  border-radius: 5px;
}

.menu a{
  color: white;
  padding: 10px;
}

.room-img{
  width: 100%;
  margin-top: 40px;
}
</style>
