<template>
<li >
  <input type="checkbox" >&nbsp;&nbsp;&nbsp;&nbsp;{{content}}
   <!-- <a @click="DeleteIndex" class='btn' >完成事项</a></input>
   <a @click="DeleteIndexs" class='btn' >删除事项</a></input> -->

</li>

</template>

<script>
export default {
    // name: 'TodoItem'  
    props:['content','indexs'],
    methods:{
        DeleteIndex(){
        this.$emit('delete',this.indexs)
    }
  }
}
</script>

<style scoped>

.btn {

  border: 1px solid #ccc;

  border-radius: 10px;

  cursor: pointer;

  display: inline-block;

  margin: 0px 5px;

  padding: 5px 10px;

  min-width: 30px;

  text-align: center;

  &:hover, &.active {
    background-color: blue;


    color: #fff;

  }

}
</style>>

