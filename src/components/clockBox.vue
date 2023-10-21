<template>
    <div id="clockBox">
        <div id="clock" >
            <div id="num">{{hours}}:{{minu}}</div>
        </div>
    </div>
</template>
<script>
export default{
    name:'clockBox',
    data(){
        return{
            minu:'0',
            hours:'0'
        }
    },
    methods: {
        getTime(){
            let d = new Date();
            let m = d.getMinutes();
            let r = d.getHours();
            if (m<10) {
                m='0'+m;
            }
            if (r<10) {
                r='0'+r;
            }
            this.minu = m;
            this.hours = r;
            return 60 - d.getSeconds();
        }
    },
    created() {
        let t = this.getTime();
        setTimeout(() =>{
            this.getTime();
            setInterval(() => {
                this.getTime();
            }, 60000);
        },t*1000);
        
    },
}
</script>
<style scoped>

#clockBox{
    margin-left:20px ;
    width: 200px;
    height: 80px;
    display: flex;
    justify-content: center;
    align-items: center;
}
#clock{
    background-image: linear-gradient(to right bottom,#FFF,var(--lingrback));
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 2rem;
    border-radius: 100px;
    padding: 10px;
    box-shadow: -2px -2px 5px 2px rgb(255, 255, 255),
    2px 2px 5px  var(--lingrback);
}
#num{
    letter-spacing: 3px;
    background-image: linear-gradient(to left top,#FFF,var(--lingrback));
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;;
    text-shadow: 3px 3px 5px rgba(0, 0, 0, 0.53);
    -webkit-text-stroke: 1px rgba(0, 0, 0, 0.667);
    border-radius: 100px;
    padding: 5px 25px;
    box-shadow:inset 2px 2px 5px rgba(65, 65, 65, 0.39),
    inset -2px -2px 2px 2px rgba(255, 255, 255, 0.05);
}
</style>