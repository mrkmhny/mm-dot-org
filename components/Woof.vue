<template>
  <div>
    <img src="~/static/profile.png" id='main-image' alt="Woof">
    <h1 id='site__title'>Mark Mahoney</h1>
  </div>  
</template>

<style>
  #main-image {
    margin: 1.2em;
    position: relative;
    width: 100px;
    height: 100px;
    border: 3px solid #fff;
    border-radius:100%;
    animation: backgroundChange 50s infinite;
  }

  @keyframes backgroundChange {
    0%   {background: rgba(102,152,204,.7);}
    20%  {background: rgba(102,204,152,.7);}
    40%  {background: rgba(152,204,102,.7);}
    60%  {background: rgba(204,152,102,.7);}
    80%  {background: rgba(152,102,204,.7);}
    100% {background: rgba(102,152,204,.7);}
  }

  #site__title {
    color:white;
    font-family:"Anton";
    text-transform: uppercase;
    animation: shadowChange 50s infinite;
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

