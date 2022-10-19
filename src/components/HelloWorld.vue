<template>
  <div class="hello">
<!--    <h1>{{ msg }}</h1>-->
    <a-button type="primary" v-on:click="btnClick">点我</a-button>

<!--    <p>-->
<!--      For a guide and recipes on how to configure / customize this project,<br>-->
<!--      check out the-->
<!--      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.-->
<!--    </p>-->
      <img style="width: 100%" v-if="img_src != ''" alt="Vue logo" :src="img_src">
  </div>
</template>

<script>

import axios from "axios";

export default {
  name: 'HelloWorld',
  data(){
    return {
      img_src: ""
    }
  },
  props: {
    msg: String
  },
  methods: {
    btnClick(){
      let that = this;
      axios({
        method: 'get',
        url: '/api/demo/getRandom',
      }).then(function (response) {
        console.log(response.data[0].url)
        that.img_src  = response.data[0].img12801024;
      });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
