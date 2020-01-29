<template>
  <div class="hello">
    <input type="text" v-model="num"><button @click="plus()">+</button><button @click="min()">-</button><button @click="sum()">=</button>
    <div>{{num}}</div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      num: '',
      first:'',
      second:'',
      //判断加号和减号
      plusMin:true
    }
  },
  watch:{
    num(newName,oldName){
      
    //   if(newName.charAt(0) == 0&&newName.charAt(1) ==0){
        console.log(newName,oldName)
    //     this.num = 0
    //   } else if(newName.charAt(0) == 0&&newName.charAt(1) !=0){
    //     console.log("成功")
    //     console.log(newName.splice(0,1))
    //     this.num = newName.splice(0,1)
    //   }
    }
  },
  mounted () {
    
  },
  methods:{
    
    plus(){
      this.first = this.num
      this.num = this.first + "+"
      this.plusMin = true
    },
    min(){
      this.first = this.num
      this.num = this.first + "+"
      this.plusMin = false
    },
    sum(){
      if(this.plusMin){
        this.second = this.num.substring(this.num.indexOf("+")+1)
        this.num = Number(this.first) + Number(this.second)
      } else {
        this.second = this.num.substring(this.num.indexOf("-")+1)
        this.num =Number(this.first) - Number(this.second)
      }
      
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
