<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png" v-show="isShow"> -->
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <button @click="isShow =! isShow">Ẩn hiện<noframes></noframes><noscript></noscript></button>
    <div v-bind:class="{success: attrColor}">text color</div>
    <input v-model="message" placeholder="Nhập thông điệp">
    <p>Thông điệp: {{ message }}</p>
    <button v-on:click="message = 'lemon tree'">ok</button>
    <input type="text" v-model="newTask">
    <button v-on:click="tasks.push({content: newTask, status :false})">Thêm</button>
    <div v-for="(task, index) in tasks" v-bind:key="index">
      <input type="checkbox" v-model="task.status">
      <span v-bind:class="{success: task.status}">{{task.content}}</span>
      </div>
    <button @click="stepValue(2)">Counting</button>
    <div>{{count}}</div>
    <Header @runA="testEmit" />
  </div>

</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
export default {
  
  data(){
    return {
      isShow: true,
      attrColor: true,
      message: '',
      newTask: '',
      tasks: [
        { content: "spring" , status: false},
        { content: "authumn" , status: false},
        { content: "cover" , status: false},
        { content: "dance" , status: false},
      ],
      count: 0
    }
  },
  components: {
    HelloWorld,
    Header,
  },
  methods: {
    stepValue(step){
        this.count += step;
    },
    testEmit(e){
      alert(e);
    }
  },
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
.success{
  height: 20px;
  background-color: cadetblue;
}
</style>
