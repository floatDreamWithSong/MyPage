<template>
  <div id="app">
    <div id="grid-box-con" v-show="0">
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
      <div class="grid-box"></div>
    </div>
    <nav id="head">
      <clockBox/>
      <div id="pageTitle">Welcome to {{user.username}}'s Page</div>
      <userBox/>
    </nav>
    <funNav/>
    <mainBox/>
  </div>
</template>

<script>
import clockBox from './components/clockBox.vue';
import userBox from './components/userBox.vue';
import funNav from './components/funNav.vue'
import mainBox from './components/mainBox.vue'
export default {
  name: 'app',
  components: {
    clockBox,
    userBox,
    funNav,
    mainBox
  },
  data() {
    return {
      user:{
        username:'DHJ'
      }
    }
  },
}
</script>

<style>
.homeh1{
  padding: 10px 20px;
  text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.452);
  background-color: #c3d3e200;
  font-size: 2.5rem;
}
.homep{
  padding: 10px 20px;
  text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.199);
  letter-spacing: 1.5px;
  background-color: #c3d3e200;
  font-size: 1.6rem;
}
#head{
  min-width: 671px;
  top: 0;
  left: 0;
  position: absolute;
  display: flex;
  align-items: center;
  justify-content: space-between;
  box-shadow: 2px 2px 5px  var(--lingrback);
  width: 100vw;
  height: 100px;
}
#pageTitle{
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 2.4rem;
  min-width: 281px;
  padding: 0 20px;
  text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.395);
}
html{
  min-width: 671px;
  font-size:12px;
}
#grid-box-con{
  position: absolute;
  width: 80vw;
  left: 10vw;
  height: 60vh;
  top: 20vh;
  display: grid;
  grid-template-columns: repeat(auto-fill, 100px);
  gap: 50px;
  justify-content: center;
  align-items: center;
  align-content: center;
}
.grid-box{
  transition: 0.4s;
  width: 100px;
  height: 100px;
  border: 2px solid #ffffff;
  box-shadow:inset 3px 3px 5px 5px rgba(255, 255, 255, 0.4),
  inset -3px -3px 5px 5px rgba(255, 255, 255, 0.4);
  border-radius: 10px;
}
:root{
  --backblack:rgb(233, 242, 252);
  --neback:rgb(228, 237, 247);
  --lingrback:#C3D3E2;
}
@font-face {
  font-family: PlastoTrial_ExtraLight;
  font-weight: 700;
  src: url(./assets/PlastoTrial-ExtraLight.otf) format("truetype");
  text-rendering: optimizeLegibility;
}
@font-face {
  font-family: PlastoTrial_ExtraBold;
  font-weight: 700;
  src: url(./assets/PlastoTrial-ExtraBold.otf) format("truetype");
  text-rendering: optimizeLegibility;
}
#app{
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  height: 100vh;
}
*{
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  user-select: none;
  background-color: var(--backblack);
  margin: 0;
  padding: 0;
  border: 0;
}
::-webkit-scrollbar{
  width: 0;
}
</style>
