<template>
  <div class="hello">
      
    for 문 <br />
    <ul v-for="(item, idx) in items" :key="idx" @click="liClick">
        <li>{{item.name}}</li>
    </ul>
     
    ---------
      <br />
    ---------
    if else <br />
    ---------
    <p v-on:click="click">
        if click me
    </p>
    <h4 v-if="flag">
        if
    </h4>
    <h4 v-else-if="flag2">
        else if        
    </h4>
    <h4 v-else>
        else
    </h4>
    -----------------<br />
      
    인풋 text를 바로 html에 전달 <br />
    
    -------------------------<br />
     
    <input type="text" v-model="inputMsg" /> // msg 연결
    <div>
        {{inputMsg}}
    </div>
    <h3 :class="inputMsg">
        input color 
    </h3> // if input === blue color blue
    <br />
    라디오 버튼 <input type="radio" v-model="radio" value="a" />
    <h3 :class="radio==='a'? 'blue':''">
        if radio === blue
    </h3>
      
    <br>
     
      
    blue<input type=checkbox v-model="check" value="blue" />
    red<input type=checkbox v-model="check" value="red" />
    greed<input type=checkbox v-model="check" value="green" />
    <p>
        {{check}}
    </p>
    
    <p @click="click">
        click me
    </p>
      
      
    <h1>{{ msg }} </h1> <!-- {{}} 안에 msg를 바인딩  -->
    <a :href="url">naver</a> <!-- href에 url이라는 변수 바인딩 -->
    <h3 :align="align"> <!-- style 속성을 바로 바인딩 가능 -->
        align center
    </h3>
    <p :style="{color: color}"> <!-- style 바인딩 -->
        color
    </p>
    <p v-text="msg2"> // msg2 를 binding 해서 사용</p>
    <p v-html="msg3"> // v-html은 권장되지 않는 방법
        
    </p>
    <p>
        {{msg4.substr(0,4)}}
    </p>
    <p v-text="msg4">
        msg4.substr(0,4)
    </p>
    <p>
        {{arr[0]}}
        <br>
        {{obj[0]}}
    </p>
    <h3 :class="flag2 ? 'name': ''">Installed CLI Plugins</h3>
    
  </div>
</template>

<script>
    let obj =  {0: 1, 1:2, 2:3, 3:4 };
export default {
  name: 'HelloWorld',
  // props: {
  //   msg: '뷰 입니다'
  // },
  data: function(){
      return {
          items: [
              {name:1},
              {name:2},
              {name:3}
            ],
          check:[],
          radio:'',
          inputMsg: '',
          msg: 'Vue.js',
          msg2: 'vind text',
          msg3: '<h1>hi<h1>',
          msg4: 'substring msg',
          arr: [1, 2, 3, 4],
          obj,
          align: 'right',
          color: 'skyblue',
          url: 'https://www.naver.com',
          flag: true,
      }
  },
  computed:{
      flag2 : function(){
          if(this.msg) true;
      }
  },
  methods:{
      click: function(){
          this.flag ? this.flag = false: this.flag = true
      },
      liClick:(e)=>{
          
          console.log(e.target.textContent);
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
    
.name{
    color: skyblue;
}
    .blue{
        color:blue;
    }
</style>
