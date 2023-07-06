<template>
  <div class="hello">
    <p> {{firstrWord}} {{secWord}} </p>
   
    <!-- mmkn nktb v-bind:class="..." or :class="..." -->
    <h1 v-bind:class="classes">color</h1>
    <a v-bind:href="googlewebsite">google</a> <br>
    <input type="text" v-bind:value="name"><br>
     <p>{{salary}}</p>
    <button v-on:click="salary++"> click to +1</button><br>
    <button v-on:click="salary--"> click to -1</button><br>
    <button v-on:click="schangeSalary(10)"> changeSalary</button><br>

    <button v-on:click="say('hi')">Say Hi</button>
    <button v-on:click="say('what')">Say What</button> <br>

    <h2>{{title}}</h2>
    <input type="text" v-model="title">

    <input type="checkbox" id="check" v-model="checked">
    <label for="check">{{checked}}</label>
    <br>
    <br>
    <button @click.ctrl="messsageAlert()"> ctrl+ click to show the alert message </button>
    <h1 v-if="type">selected true</h1>
    <button v-on:click="changeType()">show or hide </button> <br>

    <div v-if="type1==='admin'"> 
      admin
    </div>
    <div v-else-if="type1==='user'"> 
      user
    </div>
    <div v-else> 
      pls log in
    </div> <br>
    <div v-for="item ,index in items"> {{index}} {{item}}</div> 
    <br> <br>
    <div v-for="st in student"> {{st.s_name}} {{st.s_age}}</div>

    


    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  // this code is use for data
  // new Vue(){
  //   el:'#app',
  //   data:{
  //     firstData:'areege',
  //     secName:'samir',
  //   }
  // },
  
  data(){
    return{
      firstrWord:'Hello',
      secWord:'world',
      classes:['blue', 'underline'],
      googlewebsite:'https://www.google.com',
      name:'areej',
      salary:'200',
    //   changeSalary(increase){
    //     this.salary += increase
    //  },
    title:'first',
    type:true,
    type1:'aj',
    items:['blue','red','green'],
    student:[
      {s_name:'ahmed', s_age:'22'},
      {s_name:'mohamed', s_age:'22'},
      {s_name:'sayed', s_age:'22'},
    ]
    }
    
  },
  methods:{
   changeSalary(increase){
        this.salary += increase;
     },
    say(msg) {
      alert(msg)
    },
    
    messsageAlert(){
        alert('Good Job')
    },
    changeType(){
      this.type =!this.type;
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
.blue{
  color: blue;
}
.underline{
  text-decoration: underline;
}
</style>
