<template>

  <Modal @closeModal="모달창열렸니 = false" :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니" />
  
  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{a}}</a>
  </div>
  
  <Discount/>

  <Card @openModal="모달창열렸니 = true; 누른거 = $event" 
  :원룸="원룸들[i]" v-for="(a,i) in 원룸들" :key="a"/>
  
  
  <!-- <div v-for="(a,i) in 원룸들" :key="i"> 
    <img :src="원룸들[i].image" class="room-img">
    <h4 @click="모달창열렸니 = true; 누른거 = i">{{a.title}}</h4>
    <p>{{a.price}}원</p>
  </div>
  -->
  
  
  
  </template>
  
  <script>

  
  
  import data from './assets/oneroom.js';
  import Discount from './Discount.vue';
  import Modal from './Modal.vue';
  import Card from './Card.vue';


  
  
  export default {
    name: 'App',
    data(){
      return {
        오브젝트 : { name : 'kim', age : 20 },
        누른거 : 0,
        원룸들 : data,
        모달창열렸니 : false,
        신고수 : [0,0,0],
        메뉴들 : ['Home', 'Shop', 'About'],
        products : ['역삼동원룸', '천호동원룸', '마포구원룸'],

  
      }
    },
    methods : {
      increate(){
        this.신고수 +=1;
      }
    },
  
    components: {
    Discount: Discount,
    Modal: Modal,
    Card : Card,
}
  }
  </script>
  
  <style>
    body{
      margin: 0
    }
    div {
      box-sizing: border-box;
    }
    .discount{
      background: #eee;
      padding: 10px;
      margin: 10px;
      border-radius: 5px;
    }
    .black-bg {
      width: 100%; height: 100%;
      background-color: rgba(0, 0, 0, 0.5);
      position: fixed; padding: 20px;
    }
    .white-bg {
      width: 100%; background: white;
      border-radius: 8px;
      padding: 20px;
    }
    .room-img{
      width: 100%;
      margin-top: 40px;
    }
  
    h4{
      color: blue;
    }
  
    div{
      text-align: center;
    }
  
    .menu {
      background: darkslateblue;
      padding: 15px;
      border-radius: 5px;
    }
  
    .menu a{
      color: white;
      padding: 10px
    }
  
    
  </style>
  
  