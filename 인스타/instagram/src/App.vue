<template>
<div class="header">
    <ul class="header-button-left">
      <li>Cancel</li>
    </ul>
    <ul class="header-button-right">
      <li>Next</li>
    </ul>
    <img src="./assets/logo.png" class="logo" />
  </div>

  <Container :instaData="instaData" :step="step"/>
  <button @click="more">더 보기</button>

  <div class="footer">
    <ul class="footer-button-plus">
      <input @change="upload" type="file" id="file" class="inputfile" />
      <label for="file" class="input-plus">+</label>
    </ul>
 </div>



  <button @click="step = 0">피드</button>
  <button @click="step = 1">필터선택</button>
  <button @click="step = 2">게시물등록</button>


</template>

<script>
import Container from './components/Container.vue'
import instaData from './assets/instaData.js'
import  axios from 'axios'


export default {
  name: 'App',
  components: {
    Container
  },
  data(){
    return{
    instaData : instaData,
    pageIndex : '0',
    step : 0,
    }
  },
  methods: {
    more(){
                                        // 실패했을 경우에는 catch, 성공했을 때는 then,

      axios.get(`https://codingapple1.github.io/vue/more${this.pageIndex}.json`).then((result) =>{
        this.instaData.push(result.data)
        this.pageIndex ++ 
      }
      ).catch(()=>{alert('마지막 게시물입니다')})
    },
    upload(e){
      e.target.files
    }
  },

}
</script>

<style src = "./assets/style.css">


</style>
