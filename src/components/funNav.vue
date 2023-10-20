<template>
    <div id="funNav">
        <div id="funwel" class="funitem pressed">Home</div>
        <div id="funblog" class="funitem">Blogs</div>
        <div id="funpro" class="funitem">Project</div>
        <div id="funre" class="funitem">Board</div>
    </div>
</template>
<script>
export default{
    name:'funNav'

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
    cursor: pointer;
    -webkit-text-stroke: 1px black;
    transition: .4s;
    color: transparent;
    font-size: 1.5rem;
    padding: .5rem 1rem;
    border-radius: 10px;
}
.pressed{
    text-shadow: -1px -1px  rgb(0, 0, 0);
    font-weight: 900;
    box-shadow:inset 3px 3px 4px var(--lingrback),inset -3px -3px 3px rgba(255, 255, 255, 0.799);
}
</style>