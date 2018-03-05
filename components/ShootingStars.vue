<template>
  <div id='shooting-stars'>
    <div class="star s-1"></div>
    <div class="star s-2"></div>
    <div class="star s-3"></div>
  </div>
</template>

<style>
  .star {
    position:fixed;
    left:0px;
    top:50px;
    width:1px;
    height:1px;
    background-color:white;
    position:fixed;
    animation-name: particleAnimation;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
  }

  .star::before{
    position:absolute;
    display:block;
    content:"";
    width:100px;
    right:1px;
    top:0px;
    height:1px;
    background: linear-gradient(to right, rgba(0,0,0,0) 0%,rgba(255,255,255,0.4) 100%); 
  }

  .s-1{
    animation-duration:10s;
  }
  .s-2{
    animation-duration:5s;
    top:30%;
  }
  .s-3{
    animation-duration:20s;
    top:90%;
  }

  @keyframes particleAnimation {
    from { left: -100px; }
    to { left: calc( 100% + 100px );}
  }
</style>
