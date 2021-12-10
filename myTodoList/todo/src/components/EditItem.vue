<template>
  <div>
      <div class="list-table edit-list">
      <table>
        <col style="width:10%">          
        <col style="width:10%">          
        <col style="width:10%">          
        <col style="width:50%">          
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


        </tr>

        
        <tr>
            <td><input type="text"></td>   
            <td>
                <select name="" id="">
                <option value="">기획팀</option>
                <option value="">퍼블팀</option>
                <option value="">디자인팀</option>
                <option value="">개발팀</option>
                </select>
            </td>   
            <td>
                <select name="" id="">
                <option value="">기획팀</option>
                <option value="">퍼블팀</option>
                <option value="">디자인팀</option>
                <option value="">개발팀</option>
                </select>
            </td>   
            <td><input type="text"></td>   
            <td><select name="" id="">
                <option value="">대기중</option>
                <option value="">진행중</option>
                <option value="">완료</option>
                </select></td> 

        </tr>

        
      </table>
    <div class="confirm-wrap">
        <button class="confirm" @click="gotoList">수정</button>
    </div>

  </div>
  </div>
</template>

<script>
export default {
    methods: {
        gotoList(){
            this.$emit('gotoList')
        }
    },
}
</script>

<style>

</style>