<template>
  <div v-on:click="play" id='ship'>
    <div id='craft'>
      <div id='hull'></div>
      <div id='window'></div>
      <div id='left-wing'></div>
      <div id='center-wing'></div>
      <div id='right-wing'></div>
    </div>
    <div id='fire' class>  
      <div id='tail'></div>
    </div>  
  </div>
</template>

<script>
export default {
  methods: {
    play: function() {
      var audio = new Audio('http://soundbible.com/mp3/Elevator Ding-SoundBible.com-685385892.mp3')
      audio.play();
    }
  }
}
</script>


<style>
  #ship {
    z-index: 1;
    width: 100px;
    height: 200px;
    top: 0;
    left:0;
    position: absolute;
    display: flex;
    justify-content: flex-start;
    flex-direction: column;
    animation: flyBy 10s both linear 4s;
  }

  #craft {
    position: inherit;
    width: 100%;
    height: 35%;
    display: flex;
    justify-content: center;
  }

  #hull {
    height: 100%;
    width: 45%;
    background: rgba(102,234,172,1);
    border-radius: 100px 100px 20px 20px;
  }

  #window {
    position: absolute;
    width: 15px;
    height: 15px;
    background: #BE2E6B;
    border-radius: 50%;
    margin: 12% auto;
    border: .2em solid #562449;
    animation: window 3s infinite linear;
  }

  #left-wing {
    position: absolute;
    left:12%;
    top: 60%;
    height: 0;
    width: 5px;
    border-bottom: 20px solid #BE2E6B;
    border-left: 10px solid transparent;
    animation: leftWing 3s infinite linear;

  }

  #right-wing {
    position: absolute;
    top: 60%;
    left: 74%;
    height: 0;
    width: 5px;
    border-bottom: 20px solid #BE2E6B;
    border-right: 10px solid transparent;
    animation: rightWing 3s infinite linear;
  }

  #center-wing {
    position: absolute;
    top: 22px;
    width: 2px;
    margin: 0 auto;
    background: transparent;
    height: 20px;
    border-bottom: 20px solid #BE2E6B;
    border-right: 2px solid transparent;
    border-left: 2px solid transparent;
    animation: centerWing 3s infinite linear;
  }

  #fire {
    position: inherit;
    display: flex;
    justify-content: center;
    margin-top: 70px;
    width: 100%;
    height: 30%;
  }

  #tail {
    position: relative;
    margin-top: 5px;
    width: 0px;
    height: 0px;
    border-radius: 40px 40px 0px 0px;
    border-style: solid;
    border-width: 80px 24px 0 24px;
    border-color: rgb(190, 46, 46) transparent transparent transparent;
    animation: burn .4s infinite linear;
  }

  /* ANIMATIONS */
  @keyframes flyBy {
    0% {transform: translate(-150px, 80vh) rotate(45deg)}
    100% {transform: translate(100vw, -200px) rotate(45deg)}
  }

  @keyframes burn {
    0%   {transform: scaleY(1.8); transform-origin: top}
    25%  {transform: scaleY(1.2); transform-origin: top}
    50%  {transform: scaleY(1.5); transform-origin: top}
    75%  {transform: scaleY(1); transform-origin: top}
    100% {transform: scaleY(1.8); transform-origin: top}
  }

  @keyframes window {
    0%   { transform: translateX(0%) scaleX(1); }
    25%  { transform: translateX(15px) scaleX(0.8); transform-origin: left}
    50%  { transform: translateX(0%) scaleX(1) }
    75%  { transform: translateX(-15px) scaleX(0.8); transform-origin: right}
  }

  @keyframes centerWing {
    0%   { transform: translateX(0%) skew(0deg) scaleX(1); }
    25%  { transform: translateX(15px) skew(12deg) scaleX(1.3); transform-origin: right}
    50%  { transform: translateX(0%) skew(0deg) scaleX(1)}
    75%  { transform: translateX(-15px) skew(-12deg) scaleX(1.3); transform-origin: left}
  }

  @keyframes leftWing {
    0%   { transform: translateX(0%) scaleX(1); }
    25%  { transform: translateX(10px) scaleX(.7); transform-origin: center}
    50%  { transform: translateX(0%) scaleX(1)}
    75%  { transform: translateX(1px) scaleX(.5); transform-origin: right}
  }

  @keyframes rightWing {
    0%   { transform: translateX(0%) scaleX(1); }
    25%  { transform: translateX(-1px) scaleX(.5); transform-origin: left}
    50%  { transform: translateX(0%) scaleX(1)}
    75%  { transform: translateX(-10px) scaleX(.7); transform-origin: center}
  }
</style>
