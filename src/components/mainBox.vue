<template>
    <div id="mainBox">
        <div id="maintext">
            <div id="hometext" v-show="index==1"></div>
            <ul v-show="index==2">
                <li class="liit">
                    <h1>Title</h1>
                    <p>
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Repellendus sunt ducimus aperiam accusamus laudantium eligendi quisquam! Laborum nam autem cumque odit, ratione incidunt dignissimos nemo suscipit id voluptatibus blanditiis quasi.
                    </p>
                </li>
                <li class="liit">
                    <h1>Title</h1>
                    <p>
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Repellendus sunt ducimus aperiam accusamus laudantium eligendi quisquam! Laborum nam autem cumque odit, ratione incidunt dignissimos nemo suscipit id voluptatibus blanditiis quasi.
                    </p>
                </li>
                <li class="liit">
                    <h1>Title</h1>
                    <p>
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Repellendus sunt ducimus aperiam accusamus laudantium eligendi quisquam! Laborum nam autem cumque odit, ratione incidunt dignissimos nemo suscipit id voluptatibus blanditiis quasi.
                    </p>
                </li>
                <li class="liit">
                    <h1>Title</h1>
                    <p>
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Repellendus sunt ducimus aperiam accusamus laudantium eligendi quisquam! Laborum nam autem cumque odit, ratione incidunt dignissimos nemo suscipit id voluptatibus blanditiis quasi.
                    </p>
                </li>
                <li class="liit">
                    <h1>Title</h1>
                    <p>
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Repellendus sunt ducimus aperiam accusamus laudantium eligendi quisquam! Laborum nam autem cumque odit, ratione incidunt dignissimos nemo suscipit id voluptatibus blanditiis quasi.
                    </p>
                </li>
                <li class="liit">
                    <h1>Title</h1>
                    <p>
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Repellendus sunt ducimus aperiam accusamus laudantium eligendi quisquam! Laborum nam autem cumque odit, ratione incidunt dignissimos nemo suscipit id voluptatibus blanditiis quasi.
                    </p>
                </li>
                <li class="liit">
                    <h1>Title</h1>
                    <p>
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Repellendus sunt ducimus aperiam accusamus laudantium eligendi quisquam! Laborum nam autem cumque odit, ratione incidunt dignissimos nemo suscipit id voluptatibus blanditiis quasi.
                    </p>
                </li>
                <li class="liit">
                    <h1>Title</h1>
                    <p>
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Repellendus sunt ducimus aperiam accusamus laudantium eligendi quisquam! Laborum nam autem cumque odit, ratione incidunt dignissimos nemo suscipit id voluptatibus blanditiis quasi.
                    </p>
                </li>
                <li class="liit">
                    <h1>Title</h1>
                    <p>
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Repellendus sunt ducimus aperiam accusamus laudantium eligendi quisquam! Laborum nam autem cumque odit, ratione incidunt dignissimos nemo suscipit id voluptatibus blanditiis quasi.
                    </p>
                </li>
                <li class="liit">
                    <h1>Title</h1>
                    <p>
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Repellendus sunt ducimus aperiam accusamus laudantium eligendi quisquam! Laborum nam autem cumque odit, ratione incidunt dignissimos nemo suscipit id voluptatibus blanditiis quasi.
                    </p>
                </li>
                <li class="liit">
                    <h1>Title</h1>
                    <p>
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Repellendus sunt ducimus aperiam accusamus laudantium eligendi quisquam! Laborum nam autem cumque odit, ratione incidunt dignissimos nemo suscipit id voluptatibus blanditiis quasi.
                    </p>
                </li>
            </ul>
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
            index:2,
            message:['Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptate, corporis dolorem obcaecati animi quis laborum adipisci neque numquam necessitatibus totam veritatis autem reprehenderit porro ad iusto vel expedita fugit delectus.',
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptate, corporis dolorem obcaecati animi quis laborum adipisci neque numquam necessitatibus totam veritatis autem reprehenderit porro ad iusto vel expedita fugit delectus.',
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptate, corporis dolorem obcaecati animi quis laborum adipisci neque numquam necessitatibus totam veritatis autem reprehenderit porro ad iusto vel expedita fugit delectus.',
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptate, corporis dolorem obcaecati animi quis laborum adipisci neque numquam necessitatibus totam veritatis autem reprehenderit porro ad iusto vel expedita fugit delectus.']
        }
    },
    methods: {
        initialWelcome(){
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
        }
    },
    mounted(){
        Event.$on('changeIndex',data=>{
            this.index=data;
        })
    },
    created() {
        this.initialWelcome();
        Event.$emit('navIndex',this.index)
    }

}
</script>
<style scoped>
ul{
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
}
.liit{
    position: relative;
    transition: .4s;
    margin: 1rem 2rem 0 2rem;
    border-radius: 10px;
    padding: 15px 30px;
    box-shadow: 2px 2px 5px var(--lingrback);
    background-image: linear-gradient(to right bottom,#ffffff61,#c9c9c92b);
}
.liit>h1{
    position: relative;
}
.liit>p{
    position: relative;
}
.liit:hover{
    cursor: pointer;
    box-shadow: 2px 2px 10px 2px var(--lingrback),-2px -2px 5px 3px rgba(173, 173, 173, 0.091);
    padding: 20px 30px;
    transition: .4s;
}
.liit::before{
    border-radius: 10px;
    transition: .5s;
    content: '';
    position: absolute;
    background-image: linear-gradient(to right bottom,#ffffff5f,#c9c9c92b);
    top: 0;
    right: 0;
    width:0;
    height: 100%;
}
.liit:hover::before{
    left: 0;
    transition: .5s;
    width: 100%;
}
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