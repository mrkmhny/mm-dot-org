<template>
  <div id='cover__container' v-bind:class='{collapsed: collapsed}'>
    <div id='cover'>
      <img src="~/static/profile.png" id='cover__main-image' alt="Woof">
      <span id='cover__title__container'>
        <h1 id='cover__title'>Mark Mahoney</h1>
      </span>
      <hr class='cover__divider__large'>
      <span id='cover__subtitle__container'>
        <h4 id='cover__subtitle'>Product Developer</h4>
      </span>
      <hr class='cover__divider__small'>
      <div id='cover__buttons'>
        <button @click='collapse' class='cover__button__wide b-1'>About</button>
        <button class='cover__button__circle b-2'><i class="fab fa-linkedin"></i></button>
        <button class='cover__button__circle b-3'><i class="fab fa-github"></i></button>
        <button class='cover__button__circle b-4'><i class="fas fa-envelope"></i></button>
      </div>
    </div>  
    <!-- <img id='octo' src="~/static/octopus.png" alt="Dr. Octopus"> -->
    <Rocket />
    <ShootingStars />
  </div>
</template>

<script>
import Rocket from '~/components/Rocket';
import CoolButton from '~/components/CoolButton';
import ShootingStars from '~/components/ShootingStars';
export default {
  components: { Rocket, CoolButton, ShootingStars },
  data: function() { return {
    aNumber: 5,
    collapsed: false,
    test: 'hello',
    test2: function() { return 'yo'}
  }},
  methods: {
    collapse: function() { 
      console.log('ayoo')
      this.collapsed = true;
      }
  }
}
</script>


<style lang='scss'>

  #cover__container {
    height:100vh;
    width:100%;
    min-width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    overflow: hidden;
    position: absolute;
    background: linear-gradient(140deg,rgba(68, 68, 68, 0.6) 20%, rgba(0, 0, 0, 0.2)), url('~/static/bg.jpg') #666666;

    &.collapsed {
      width: 100px;
      min-width: 100px;
      transition: 1s all 1s;
    }
  

    #cover {
      z-index: 2;
      display: flex; flex-direction: column;
      align-items: center;
      padding: 1.2em;
      margin: auto auto;
    }
    &.collapsed #cover {
      
    }

    #cover__main-image {
      margin: .5em;
      position: relative;
      width: 100px; height: 100px;
      border: 3px solid #fff;
      border-radius:100%;
      background: rgba(102,152,204,.7);
      animation: spinGrow 1s both 1s, backgroundChange 50s infinite linear;
    }
    &.collapsed #cover__main-image {
      animation: rollOffScreen 2s both 1s ease-in;
    }

    .cover__divider {
      @mixin cover__divider {
        width: 100%;
        min-height:1px;
        border: 0;
        margin: 0;
        background: rgba(255,255,255,.3);
      }

      &__large {
        @include cover__divider();
        width: 100%;
        margin-bottom: 1em;
        animation: slideFromLeft 1s ease-out both 1s;
      }

      &__small {
        @include cover__divider();
        width: 50%;
        animation: sink 1s both 2.5s, appear .1s both 2.5s;
      }
    }

    &.collapsed .cover__divider {
      &__large { animation: shrinkX .5s both .7s; }
      &__small { animation: disappear .01s both .7s, dividerRiseOut .4s both .3s}
    }


    #cover__title__container {
      overflow:hidden;
      margin: 0px;
      padding: 0px;
      min-height: 5em;
    }

    #cover__title {
      color:white;
      font-family:"Anton";
      font-weight: 100;
      line-height: 1em;
      font-size: 2.5em;
      text-transform: uppercase;
      animation: riseIn 3s both 1.5s, shadowChange 50s infinite linear;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: antialiased;
    }
    &.collapsed #cover__title {
      animation: sinkOut .5s both, shadowChange 50s infinite linear;
    }

    #cover__subtitle__container {
      overflow:hidden;
      margin: 0 ;
      padding: 0px;
      height: 3em;
      min-height: 3em;
      animation: sink 1s both 2.5s;
    }

    #cover__subtitle {
      color:white;
      font-family:"Raleway";
      font-weight: 900;
      line-height: 1em;
      margin: 0;
      animation: stayStill 1s both 2.5s;
    }
    &.collapsed #cover__subtitle {
      animation: subtitleRiseOut 2s both;
    }

    #cover__buttons {
      display: flex;
      justify-content: center;
    }
    &.collapsed #cover__buttons {
      transition: 1s all;
      opacity: .0;
    }

    .cover__button {
      @mixin cover__button {
        background: rgba(15,15,15,.8);
        color: silver;
        line-height: 18px;
        vertical-align: center;
        border: 1px solid grey;
        font-weight: 600;
        font-family: 'Raleway';
        letter-spacing: 1px;
        margin: auto 5px;
        height: 40px;
        transition: .3s all ease-in-out;
        outline:none;
        &:hover {
          border-color: white;
          color: white;
          background: rgba(15,15,15,.9);
        }
        &.b-1 {animation: appear 1s both 3s}
        &.b-2 {animation: appear 1s both 3.2s}
        &.b-3 {animation: appear 1s both 3.4s}
        &.b-4 {animation: appear 1s both 3.6s}
      }

      &__wide {
        @include cover__button();
        font-size: 16px;
        border-radius: 100px;
        padding: 9px 21px;
      }

      &__circle {
        @include cover__button();
        font-size: 18px;
        border-radius: 100%;
        width: 40px;
      }
    }



    #octo {
      width: 250px;
      height: 250px;
      position: absolute;
      animation: floatAway 10s both;
    }

  }

   //////////////
  // ANIMATIONS //
   //////////////
   


  @keyframes slideFromLeft { 
    0% {transform: translateX(-200vw)} 
  }

  @keyframes riseIn { 
    0%   {transform: translateY(200%)}
    100% {transform: translateY(0%)}   
  }
  @keyframes sinkOut {
    0%   {transform: translateY(0%)}
    10%   {transform: translateY(-10%)}
    100% {transform: translateY(200%)}   
  }

  @keyframes subtitleRiseOut {
    0%   {transform: translateY(1em)}
    100% {transform: translateY(-400%)}  
  }
  @keyframes dividerRiseOut {
    0%   {transform: translateY(-1em)}
    100% {transform: translateY(-4em)}  
  }

  @keyframes stayStill {
    0%   {transform: translateY(4em)}
    100% {transform: translateY(1em)}
  }
  @keyframes sink { 
    0%   {transform: translateY(-4em)}
    100% {transform: translateY(-1em)}   
  }

  @keyframes growY { 
    0%   {transform: scaleY(0); transform-origin: top} 
    100% {transform: scaleY(1)} 
  }

  @keyframes shrinkX { 
    0%   {transform: scaleX(1)} 
    100% {transform: scaleX(0)} 
  }

  @keyframes appear {
    0%   {opacity: 0}
    100% {opacity: 1}
  }

    @keyframes disappear {
    0%   {opacity: 1}
    100% {opacity: 0}
  }

  @keyframes spinGrow {
    0%   {transform: rotate(0deg) scale(0);}
    100% {transform: rotate(360deg) scale(1);}
  }

  @keyframes rollOffScreen {
    0%   {transform:  rotate(0deg); left:0}
    100% {transform:  rotate(-2080deg); left:-300vw;}
  }

  @keyframes floatAway {
    0% {transform: rotate(0deg) translate(-500px, random(300)+px)}
    100% {transform: rotate(360deg) translate(9999px, random(300)+px)}
  }

  
  @keyframes backgroundChange {
    0%   {background: rgba(102,152,204,.7);}
    20%  {background: rgba(102,204,152,.7);}
    40%  {background: rgba(152,204,102,.7);}
    60%  {background: rgba(204,152,102,.7);}
    80%  {background: rgba(152,102,204,.7);}
    100% {background: rgba(102,152,204,.7);}
  }

  @keyframes shadowChange {
    0%   {text-shadow:2px 3px 0px rgba(102,152,204,.7);}
    20%  {text-shadow:2px 3px 0px rgba(102,204,152,.7);}
    40%  {text-shadow:2px 3px 0px rgba(152,204,102,.7);}
    60%  {text-shadow:2px 3px 0px rgba(204,152,102,.7);}
    80%  {text-shadow:2px 3px 0px rgba(152,102,204,.7);}
    100% {text-shadow:2px 3px 0px rgba(102,152,204,.7);}
  }
</style>

