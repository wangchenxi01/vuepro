<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input type="text" v-model="message" placeholder="say something...">
    <button style="margin-left: 10px;" @click="onsubmit">submit</button>
    <button style="margin-left: 10px;" @click="save">save</button>
    <button style="margin-left: 10px;" @click="showHistory">showHistory</button>
    <ul>
      <li style="width:100%;color:pink" v-for="(item,index) in messageArr" :key="index">
        内容：{{item.message}}
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HelloWorld',
  // data:{
  //   message: String
  // },
  props: {
    messageArr:[],
    localdataArr:[],
    words:[],
    message: String,
    msg: String,
    saveflg:Boolean
  },
  created:function(){
      this.message=''
      this.words = ['你还没输入呢','are u kidding me?','入力してください','i dont know u mean','-_-||']
      this.messageArr = []
        this.localdataArr = []
  },
  methods:{
    onsubmit(){
      var m = parseInt(Math.random()*5,10); 
      if(this.message.length == 0){
         alert(this.words[m]);
      }else{
        this.messageArr.push({message: this.message})
        // this.localdataArr.push({message: this.message})
        this.message=''
      }
      // alert(this.messageArr.length);
    },
    showHistory(){
        let data1 = JSON.parse(localStorage.getItem('localData'))
        if(this.messageArr){
          if (this.saveflg)
          // this.messageArr = this.messageArr.concat(data1)
          this.messageArr = []
          this.messageArr = data1
          this.saveflg = false
        }else{
          this.messageArr = []
          this.messageArr = data1
        }
    },
    save(){
      if(this.messageArr){
        localStorage.setItem('localData', JSON.stringify(this.messageArr));
        this.saveflg = true
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: red;
}
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
