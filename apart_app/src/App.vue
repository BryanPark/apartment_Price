<template>
  <div class="menu">
    <a v-for = "(a, i) in menus" :key="i">{{a}}</a>
  </div>
  <img alt="Vue logo" src="./assets/logo.png">
  <div class="selling_item" v-for="a,i in products" :key="i">
    <h4>{{a}}</h4>
    <p>{{price[i]}}만원</p>
    <button @click="increaseReportCnt(i)">허위매물신고</button> <span>신고수 : {{reportCnt[i]}}</span>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      price : [60, 40, 50],
      products:["역삼동원룸", "천호동원룸", "마포구원룸"],
      menus:["Home", "Products", "About"],
      reportCnt: [0, 0, 0],
    }
  }, 
  methods: {
    increaseReportCnt(i){
      this.reportCnt[i]++;
    }
  },
  components: {
  }
}
</script>

<style>
.menu{
  background: darkslateblue;
  padding: 1vw;
  border-radius: 2px;
}
.menu a{
  color:white;
  padding: 10vw;
}
.seling_item button{
  margin : 2vw;
}


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
