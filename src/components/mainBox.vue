<template>
    <div id="mainBox">
        <div id="maintext">
            <div id="hometext" v-show="index==1">

            </div>
        </div>
    </div>
</template>
<script>
import axios from 'axios';
import Event from '@/EventBus.vue';
export default {
    name:'mainBox',
    data() {
        return {
            index:1
        }
    },
    mounted(){
        Event.$on('changeIndex',data=>{
            this.index=data;
        })
    },
    created() {
        let t = ' ';
        axios({
            url:'http://localhost:8080/welcome.json',
            method:'get',
            headers:{
                "X-Content-Type-Options": "nosniff",
                "Content-Type":"application/json"
            }
        }).then(
        res=>{
            console.log(res);
            for (let i = 1; i < 6; i++) {
                t+='<h1 class="homeh1">'+eval('res.data.tit'+i)+'</h1><br>'+'<p class="homep">'+eval('res.data.text'+i)+'</p>';
            }
            document.getElementById("hometext").innerHTML=t;
            res;
        }
        ).catch(
        err=>{
            console.log(err);
        }
        )
        
    },

}
</script>
<style scoped>
    *{
        background: rgba(255, 0, 0, 0);
    }
    #mainBox{
        min-width: 440px;
        max-width: 1000px;
        margin-top: 30px;
        margin-bottom: 20px;
        padding: 1rem;
        border-radius: 15px;
        width: 80vw;
        min-height: 300px;
        height:60vh;
        box-shadow: 2px 2px 5px var(--lingrback),-2px -2px 4px white;
    }
    #maintext{
        overflow: scroll;
        margin-top: 1rem;
        margin-bottom: 1rem;
        border-radius: 15px;
        width:100%;
        height: 98%;
        box-shadow:inset 2px 2px 5px var(--lingrback),inset -3px -3px 4px rgba(255, 255, 255, 0.927);
    }
    #maintext::-webkit-scrollbar{
        width:0;
    }
</style>