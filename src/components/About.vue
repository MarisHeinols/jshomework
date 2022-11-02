<template>
  <div>
    <h1 class="whiteText padding-bt2">ABOUT ME</h1>
    <div class="horizontal"></div>
    <h3 class="colloredText padding-bt1">Name: {{userData.name}}</h3>
    <h3 class="colloredText padding-bt1">Surname: {{userData.surname}}</h3>
    <h3 class="colloredText padding-bt1">Code: {{userData.code}}</h3>
  </div>
</template>

<script>
export default {
  name: 'About',
  data() {
    return{
      userData:{
        name:"Maris",
        surname:"Heinols",
        code:"IT20047"
      }
    }
  },
}
</script>
<style scoped>
.padding-bt2{
padding-bottom: 2vh;
}
.padding-bt1{
  padding-bottom: 1vh;
  }
.whiteText{
  color:rgba(255, 255, 255, 0.89)
}
.colloredText{
  color:rgb(177, 22, 112)
}
.horizontal {
  border-top: 2px solid rgb(255, 255, 255);
  height: 3vh;
  width: 30vw;
  align-self: flex-start;
}
</style>

