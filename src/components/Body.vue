<template>
    <div class="bodyBox">
        <nav v-if="loggedIn">
            <router-link class="routerButton buttonText" to="/">Home<div class="routerButtonTriangle"></div></router-link> |
            <router-link class="routerButton buttonText" :to="`/about`" >About<div class="routerButtonTriangle"></div></router-link>
        </nav>
          <router-view class="content" v-if="loggedIn"/>
    </div>
</template>
<script>

export default {
    name:"Body",
    props:["loggedIn","userData"]
}
</script>
<style scoped>
.bodyBox{
    display: flex;
    padding: 5vh;
    width: 100vw;
    height: 90vh;
    background-color: rgb(29, 13, 44);
}
.routerButton{
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 20vw;
    height:4vh ;
    background-color: rgb(164, 66, 255);
    margin-right: 5vw;
    transition: width 1s, background-color 2s;
    

}
.routerButton:hover{
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 25vw;
    background-color: rgb(177, 22, 112);
    margin-right: 5vw;
    

}
.routerButtonTriangle{
    width: 0;
    height: 0;
    border-bottom: 4vw solid rgb(29, 13, 44);
    border-left: 4vh solid transparent;
}
.buttonText{
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    font-size: 1.2vw;
    font-weight: 900;
    letter-spacing: 0.15vw;
    text-decoration: none;
    color: white;
    padding-left: 1vw;
}
.content{
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-direction: column;
    width: 55vw;
    max-height: 100vh;
    position: absolute;
    left: 40vw;
    padding: 2vw;
}
</style>
