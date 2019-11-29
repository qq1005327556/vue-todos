<template>
  <div class="about">
    <div>TODOS</div>
    <!-- input -->
    <div>
      <el-input class="ipt" v-model="inputValue" placeholder="请输入内容"></el-input>
      <el-button type="primary" @click="btn_add">增加</el-button>
    </div>
    <!-- 列表 -->
    <div class="list">
      <div class="lists" v-for="(item,index) in list" :key='index+item'>
        <input type="checkbox">
        <span>{{item.title}}</span>
        <button @click="del(index)">删除</button>
      </div>
    </div>
    <div class="footer">
      <span>显示数量</span>
      <div class="tab">
        <div class="active">100</div>
        <div>100</div>
        <div>100</div>
      </div>
      <div>清空选中</div>
    </div>
  </div>
</template>
<script>
export default {
  data(){
    return{
       inputValue :'',
      list:[
        {title:'1234',},
        {title:'123224',}
      ]
    }
  },
  methods:{
    //增加
    btn_add(){
      if(this.inputValue===''){
        alert('输入框不可为空')
      }else{
      this.list.push({
        title : this.inputValue
      })
      this.inputValue =''
      }
    },
    // 删除
    del(index){
      this.list.splice(index,1)
    }
  }
}
</script>
<style scoped>
.about{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center
}
.ipt{
  width: 450px;
  margin-right: 20px;
}
.list{
  width: 500px;
  height: 100px;
  border: 1px solid #999;
  margin: auto
}
.lists{
  border-bottom:1px solid #999
}
.footer{
  width: 500px;
  height: 30px;
  border:1px solid red;
  margin:auto;
  display: flex;
  align-items: center;
  justify-content: space-between
}
.tab{
  width: 150px;
  display: flex;
  justify-content: space-between
}
.active{
  background: red;
  color: #fff
}
</style>