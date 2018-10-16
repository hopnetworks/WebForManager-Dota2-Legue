<template>
  <div class="dashboard"></div>
</template>
<script>
import axios from 'axios';

export default  {
  componentDidMount() {
    // 使用 axios 获取数据
  axios.post('https://ai.hopnetwork.com:8889/finduserbalance', {
     Name: 'Fred',
      lastName: 'Flintstone'
    })
    .then(function (response) {
      console.log(response);
    })
    .catch(function (error) {
      console.log(error);
    });
  },

}
</script>