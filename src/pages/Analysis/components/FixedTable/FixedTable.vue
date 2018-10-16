<template>
  <div className="fixed-table">
    <basic-container>
      <el-table
      :data="tableData3"
      style="width: 100%"
      height="286">
        <el-table-column
          fixed
          prop="personaname"
          label="玩家名"
          width="150">
        </el-table-column>
        <el-table-column
          prop="hero"
          label="英雄"
          width="120">
        </el-table-column>
        <el-table-column
          prop="kills"
          label="击杀"
          width="120">
        </el-table-column>
        <el-table-column
          prop="level"
          label="等级"
          width="100"
          :filters="[{ text: '家', value: '家' }, { text: '公司', value: '公司' }]"
          :filter-method="filterTag"
          filter-placement="bottom-end">
         <!-- <template slot-scope="scope">
            <el-tag
              :type="scope.row.tag === '家' ? 'primary' : 'success'"
              close-transition>{{scope.row.tag}}</el-tag>
          </template>-->
        </el-table-column>
        <el-table-column
          prop="assists"
          label="助攻"
          width="120">
        </el-table-column>
        <el-table-column
          prop="deaths"
          label="死亡"
          width="300">
        </el-table-column>
        <el-table-column
          prop="kda"
          label="kda"
          width="120">
        </el-table-column>
        <!--<el-table-column label="操作" width="180" fixed="right">
          <template slot-scope="scope">
            <el-button
              size="mini"
              @click="handleEdit(scope.$index, scope.row)">编辑</el-button>
            <el-button
              size="mini"
              type="danger"
              @click="handleDelete(scope.$index, scope.row)">删除</el-button>
          </template>
        </el-table-column>
        -->
      </el-table>
    </basic-container>
  </div>
</template>

<script>
import BasicContainer from '@vue-materials/basic-container'
import axios from 'axios'
import VueAxios from 'vue-axios'
//Vue.prototype.$http = axios
import Vue from 'vue';
Vue.prototype.$http = axios;

  export default {
  components: { BasicContainer },
  name: 'FixedTable',
  data() {
    return {
      tableData3: [
      ]
    }
  },
  methods: {

    handleEdit(index, row) {
      console.log(index, row);
    },
    handleDelete(index, row) {
      console.log(index, row);
    }
  },
  mounted:function(){

   axios.get('https://api.opendota.com/api/matches/261145478', {

     })
     .then((response) => {
      // console.log(response.data);
        console.log(response.data.players);
      this.tableData3=response.data.players;
     })
     .catch(function (error) {
       console.log(error);
     });

  },


}
</script>

<style>
  .fixed-table {

  }
</style>
