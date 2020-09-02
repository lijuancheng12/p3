<template>
  <div>
      <span/>
      <span/>
      <span/>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
div {
    position: relative;
    /*bottom: 20px;*/
    left: 50%;
    width: 40px;
    height: 40px;
    /*background: white;*/
    transform: /*translateY(-80px)*/ translateX(-50%) rotate(45deg);
    span {
        position: absolute;
        top: 0;
        left: 0;
        display: block; 
        width: 100%;
        height: 100%;
        border-bottom: 2px solid rgb(251, 251, 251);
        border-right: 2px solid rgb(251, 251, 251);
        animation: animate 1.5s linear infinite;
    }
    span:nth-child(1){
        transform: translate(-15px, -15px);
        animation-delay:-0.4s;
    }
    span:nth-child(2){
        transform: translate(0px, 0px);
        animation-delay:-0.2s;
    }
    span:nth-child(3){
        transform: translate(15px, 15px);
        animation-delay:0s;
    }
    @keyframes animate
    {
        0%{
            top:-5px;
            left:-5px;
            opacity:0;
        }
        25%{
            top:0px;
            left:0px;
            opacity:1;
        }
        50%,100%{
            top:5px;
            left:5px;
            opacity:0;
        }
    }

}
</style>