<template>
    <div id="funNav">
        <div @click="sendMesToMain(1)" id="funwel" class="funitem pressed">Home</div>
        <div @click="sendMesToMain(2)" id="funblog" class="funitem">Blogs</div>
        <div @click="sendMesToMain(3)" id="funpro" class="funitem">Project</div>
        <div @click="sendMesToMain(4)" id="funre" class="funitem">Board</div>
    </div>
</template>
<script>
import Event from '@/EventBus.vue';
export default{
    name:'funNav',
    data() {
        return {

        }
    },
    methods:{
        sendMesToMain(i){
            let a = document.getElementsByClassName("funitem");
            for (let ii = 0; ii < a.length; ii++) {
                const element = a[ii];
                element.className = ii+1==i? 'funitem pressed':'funitem';
            }
            Event.$emit('changeIndex',i);
        }
    },
    mounted() {
        Event.$on('navIndex',i=>{
            let a = document.getElementsByClassName("funitem");
            for (let ii = 0; ii < a.length; ii++) {
                const element = a[ii];
                element.className = ii+1==i? 'funitem pressed':'funitem';
            }
        })
    },
    created() {
        this.sendMesToMain(2);
    },
}
</script>
<style scoped>
#funNav{
    max-width: 1000px;
    min-width: 440px;
    display: flex;
    justify-content: space-around;
    padding: .5rem;
    width: 80vw;
    margin-top: 140px;
    border-radius: 10px;
    box-shadow: 2px 2px 5px var(--lingrback), -2px -2px 5px white;
  }
.funitem{
    transition: .3s;
    cursor: pointer;
    -webkit-text-stroke: 1px black;
    color: transparent;
    font-size: 1.5rem;
    padding: .5rem 1rem;
    border-radius: 10px;
    box-shadow:  2px 2px var(--lingrback), -2px -2px white;
}
.funitem:hover{
    transition: .3s;
    box-shadow:  0.5px 0.5px var(--lingrback), -0.5px -0.5px white;
}
.pressed:hover{
    box-shadow:inset 3px 3px 4px var(--lingrback),inset -3px -3px 3px rgba(255, 255, 255, 0.799);
}
.pressed{
    text-shadow: -1px -1px  rgb(0, 0, 0);
    font-weight: 900;
    box-shadow:inset 3px 3px 4px var(--lingrback),inset -3px -3px 3px rgba(255, 255, 255, 0.799);
}
</style>