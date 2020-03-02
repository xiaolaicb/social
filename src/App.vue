<template>
  <div id="app">
    <input type="text" v-model="username">
    <input type="password" v-model="password">
    <button v-on:click="handle">测试</button>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data(){
    return {
      username:'',
      password:''
    }
  },
  components: {  
    HelloWorld
  },
  methods:{
    handle(){
      this.$http.post('api/api/user/login',{userName:this.username,password:this.password}).then((res)=>{
        console.log(res)
      })
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
