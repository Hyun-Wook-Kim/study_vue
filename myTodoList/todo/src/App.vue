<template>
<div>
      <div class="header">
      <h2>수정사항 목록</h2>
    </div>

  <div class="listshow" v-if="step == 'list'">
    <FixList :fixdata="fixdata" @gotoEdit="step = 'edit'"></FixList>
    <div class="confirm-wrap">
      <button class="confirm register">등록</button>
    </div>
  </div>

  <div class="edit" v-if="step == 'edit'">
    <Editlist @gotoList="step='list'"></Editlist>
  </div> 

</div>
</template>

<script>

import FixList from './components/FixList.vue'
import fixdata from './assets/data.js'
import Editlist from './components/EditItem.vue'

fixdata
export default {
  name: 'App',
  components: {
    FixList : FixList,
    Editlist : Editlist,
  },
  data(){
    return{
      fixdataList : [],
      newList : "",
      fixdata : fixdata,
      step : 'list',
      index : '',
    }
  },
  methods: {
    register(){

    }
  },
  created() {
    this.fixdata.forEach(datum => {
      localStorage.setItem(datum.id, JSON.stringify(datum))
      console.log(datum)
    });
    for(let i=0; i<localStorage.length; i++){
      let newitem = JSON.parse(localStorage.getItem(`${i}`))
      console.log(newitem)
      this.fixdataList.push(newitem)
      console.log(this.fixdataList)
    }
  }


}
</script>

<style>
  @import './assets/style.css';
</style>
