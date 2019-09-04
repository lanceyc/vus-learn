<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{site}}</h1>
    <h1 v-if="flag"> 传送门：<a v-bind:href="url">{{title}}</a></h1>
    <h1 v-else>不给看</h1>
    <a  @click="getData">get数据</a>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {  
    return {
      msg: 'Welcome to Your Vue.js App 我的第一个vue项目',
       site:'我的vue项目',
       url:'http://localhost:8080/#/goods',
       title:'点击瞧瞧',
       flag:true
    }
  },
  methods:{
      getData:function(){
      this.$ajax.get('http://localhost:54407/api/take_out/GetAAA')
        .then(function (response) {
          debugger
          console.log(response);
      })
      .catch(function (error) {
        debugger
       console.log(error);
         });
      }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
