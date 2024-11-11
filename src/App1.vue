<template>
  <div>
    <p>123</p>
    <ul>
      <li v-for="item in list" :key="item.id">{{ item.title }}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';

  export default {
    data() {
      return {
        list: []
      }
    },
    mounted() {
      axios.get('https://cnodejs.org/api/v1/topics').then(res => {
        this.list = res.data
      })
    }
  }
</script>

<style lang="scss" scoped>
  $color: #0ff;
  div {
    p {
      color: $color;
    }
    a {
      color: #000;
      &:hover {
        color: #f00;
      }
    }
  }
</style>
