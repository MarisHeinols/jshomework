<template>
    <div v-bind:class= "loginStatus ? 'headerBoxChanged' : 'headerBox'">
        <div class="contentBox">
            <img class="logo" src="../assets/logo(white).svg"/>
            <h1 class="heading">KRAKEN.FM</h1>
        </div>
        <div class="contentBox">
            <transition name="slide-fade">
                <span :style="{backgroundColor: color}" class="profilePic" v-if="loginStatus" ></span>
            </transition>   
            <transition name="slide-fade">
                <h1 class="heading" v-if="loginStatus">{{fullName}}</h1>
            </transition>
            <transition name="slide-fade">
                <div class="vertical" v-if="loginStatus"></div>
            </transition>
                <button v-bind:class= "loginStatus ? 'buttonDark' : 'button'" @click="changeLoginState(),
                getUserName(),
                headerBoxChanged=!headerBoxChanged">{{loginStatus == false ?"LOGIN":"LOGOUT"}}</button>
        </div>
    </div>
</template>
<script>
export default {
    name:"Header",
    data(){
        return{
            user : {
                name:"Maris",
                surname:"Heinols",
                code:"IT20047"
            },
            fullName : "",
            loginStatus : false,
            color:"#ff0000"
        };
    },
    methods: {
        getUserName(){
            this.fullName = this.user.name + " " + this.user.surname
        },
        changeLoginState(){
            this.loginStatus = !this.loginStatus
            this.$emit("loginStateChanged",this.loginStatus)
            this.$emit("userLogedIn",this.user)
            this.getRandomColor()
        },
        getRandomColor(){
            this.color ="#" + Math.floor(Math.random() * 16777215).toString(16);
            if (this.color.length !== 7){
                getRandomColor()
            }
        }

    },
}
</script>
<style scoped>
.headerBox{
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-height: 10vh;
    padding-left: 2%;
    background-color: rgb(81, 74, 88);
    border-bottom: 4px solid rgb(164, 66, 255);
}
.headerBoxChanged{
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-height: 10vh;
    padding-left: 2%;
    background-color: rgb(164, 66, 255);
    border-bottom: 4px solid rgb(81, 74, 88);
}

.contentBox{
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;
    width: 15vw;
    max-height: 8vh;
    padding: 1%;
    margin-right: 5vw;
}
.logo{
 max-width: 5vw
}
.heading{
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    font-size: 1vw;
    font-weight: 900;
    letter-spacing: 0.15vw;
    color: white;

}
.button{
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    font-size: 1vw;
    font-weight: 900;
    letter-spacing: 0.15vw;
    color: white;
    background-color: rgb(164, 66, 255);;
    max-width: 40%;
    height: 3vh;
    border-radius: 5vh;
    border: 0;

}
.buttonDark{
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    font-size: 1vw;
    font-weight: 900;
    letter-spacing: 0.15vw;
    color: white;
    background-color: rgb(81, 74, 88);
    max-width: 40%;
    height: 3vh;
    border-radius: 5vh;
    border: 0;

}
.profilePic {
    height: 2vw;
    width: 5vw ;
    border-radius: 50%;
    border: 1px solid white;
    display: inline-block;
    margin-right: 1vw;
  }
.vertical {
    border-left: 2px solid rgb(255, 255, 255);
    height: 3vh;
    width: 3vw;
}
.slide-fade-enter-active {
transition: all .3s ease;
}
.slide-fade-leave-active {
transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
transform: translateX(15px);
opacity: 0;
}

</style>
