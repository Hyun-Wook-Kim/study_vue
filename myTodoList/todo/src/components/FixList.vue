<template>
  <div class="list-table fix-list">
      <table>
        <col style="width:10%">          
        <col style="width:10%">          
        <col style="width:10%">          
        <col style="width:50%">          
        <col style="width:10%">    
        <col style="width:10%">    

        <tr>
            <th>
                제목
            </th>
            <th>
                from
            </th>
            <th>
                to
            </th>
            <th>
                상세내역
            </th>
            <th>
                상태
            </th>
            <th>
            </th>

        </tr>

        
        <tr v-for="(datum, index) in fixdata" :key="index">
            <td> {{datum.title}} </td>   
            <td> {{datum.from}} </td>   
            <td> {{datum.to}} </td>   
            <td> {{datum.detail}} </td>   
            <td> {{datum.condition}} </td> 
            <td class="button-wrap">
                <button @click="gotoEdit(index)">수정</button>
                <button>삭제</button>
            </td>
        </tr>

        
      </table>


  </div>
</template>

<script>
export default {
    name: 'FixList',
    props : {
        fixdata : Object,
    },
    data(){
        return {
            index: '',
        }
    },

    methods: {
        gotoEdit(index){
            this.index = index
            console.log(this.index)
            this.$emit('gotoEdit', this.index);
        }
    },
}
</script>

<style>

</style>