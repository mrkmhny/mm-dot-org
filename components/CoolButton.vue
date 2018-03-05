<template>
  <button class='cool-button'>
    Button
  </button>
</template>

<style lang='scss'>
  .cool-button {
    position: relative;
    padding: 25px 30px;
    background: transparent;
    text-transform: uppercase;
    color: #fff;
    letter-spacing: 3px;
    font-size: 14px;
    font-family:'Raleway';
    opacity: .9;
    border: 0;
    &:after, &:before {
      mix-blend-mode: multiply;
      content: "";
      position: absolute;
      width: 100%;
      height: 100%;
      transition: all .3s ease-in-out;
      z-index:-1;
      opacity: .9;
    }
    &:before {
      top: 5px;
      left: 5px;
      background: pink;
    }
    &:after {
      background: skyblue;
      top: -5px;
      left: -5px;
    }
    &:hover:after, &:hover:before {
      top: 0px;
      left: 0px;
    }
  }
</style>
