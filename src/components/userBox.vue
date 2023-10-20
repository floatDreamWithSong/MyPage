<template>
    <div id="userBox">
        <div id="usertext">
            <div id="username">
                {{user.username}}
            </div>
            <div id="userqq">{{user.userqq}}</div>
        </div>
        <div id="k">
            <div id="imgbox">
                <img id="userimg" :src="getUserImg()" alt="userimg">
            </div>
            <div id="statuscolor">
            </div>
        </div>
    </div>
</template>
<script>
export default{
    name:'userBox',
    data() {
        return {
            user:{
                username:'DHJ',
                userqq:956968770,
                status:'online'
            }
        }
    },
    methods:{
        getUserImg(){
            return 'https://q4.qlogo.cn/g?b=qq&nk='+this.user.userqq+'&s=40'
        }
    }
}

</script>
<style scoped>
*{
    background: rgba(0, 255, 255, 0);
}
#k{
    display: flex;
    flex-direction:row;
}
#statuscolor{
    background-image: linear-gradient(to right bottom,#2f9b17,rgb(101, 239, 101));
    box-shadow: 2px 2px 10px greenyellow;
    width: 1rem;
    height: 1rem;
    border-radius: 100px;
    position: relative;
    top: 30px;
    left: -10px;
}

#userBox{
    margin-right: 2rem;
    background-image: linear-gradient(to right bottom,#ffffff,#c9c9c92b);
    padding-top: 1rem;
    border-radius: 10px;
    box-shadow: 2px 2px 5px var(--lingrback),
    -2px -2px 5px white;
    display: flex;
    justify-content: space-around;
    align-items: flex-start;
    width: 200px;

}
#usertext{
    gap: .4rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
#username{
    padding: 5px 10px;
    border-radius: 10px;
    font-size: 1.5rem;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.388);
}
#userqq{
    margin-top: -4px;
    margin-bottom: 4px;
    padding: .2rem 1rem;
    text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.388);
    font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;

}
img{
    border-radius: 1000px;
}
#imgbox{
    box-shadow: 2px 2px 4px var(--lingrback), -2px -2px 4px rgb(255, 255, 255);
    background-image: linear-gradient(to left top,#FFF,var(--lingrback));
    width: 40px;
    height: 40px;
    overflow: hidden;
    border-radius: 1000px;
}

</style>