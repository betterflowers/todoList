<template>
  <div id="app">
    This is a TodoList
    <br/>
    <br>
    <div>
      <input v-model="inputValue" @keyup.enter="handleSumit" placeholder="添加 ToDo"/>
      <button @click="handleSumit">提交</button><br>
    </div>
    
    <!-- <todo-item
    v-if="item.status == 1"
    v-for="(item,index) of list"
    :key="index" 
    :content="item.inputValue" 
    :indexs="index"
    @delete="handleDeletes"
    @click="changeStatusDone" 
    </todo-item>-->
  
   <ul class="a">
     <h3 align="center">正在进行</h3>
      <li v-if="item.status == 1" v-for="(item,key) of list">{{item.inputValue}}
        <button @click="changeStatusDone(key)" :key="key">完成事项</button>
        <button @click="DeleteStatus(key)" :key="key">删除事项</button>
      </li>
     
    </ul>
    <hr>
<h3 align="center">已经完成</h3>
    <ul>
      <li v-if="item.status == 2" v-for="(item,key) of list">{{item.inputValue}}</li>
    </ul>

  </div>
</template>

<script>
import TodoItem from './components/TodoItem'

export default {
  //  name: 'TodoList',
  components:
  {
    'todo-item':TodoItem 
  },
  data(){
    return{
      inputValue:'',
      list:[] 
    }
  },
  methods:{
    handleSumit(){
      var obj ={
        inputValue:this.inputValue,
        status:1
      }
      this.list.push(obj)
      this.inputValue=''
      
    },

    changeStatusDone(key){
      this.list[key].status = 2
    },

    changeStatusDoing(key){
      this.list[key].status =1
    },

    DeleteStatus(key){
      this.list[key].status = 3
    },
    
    handleDeletes(indexs)
    {

      this.list.splice(indexs,1)
    }
  }
}
</script>

<style>
body {
  background-color:#ccc;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
li:hover {
  cursor: pointer;
}
.a
{
 list-style-type:circle;
 list-style-position:inside;
 
}
</style>
