<template>
  <div id="app">
    <router-view/>
    <div class="footer">
      <a href="https://github.com/mathyou9/">Matthew's Github</a>
    </div>
  </div>
</template>

<style>

  @font-face{
    font-family: fontOne;
    src: url(assets/font1.ttf);
  }
  @font-face{
    font-family: fontTwo;
    src: url(assets/font2.ttf);
  }
  @font-face{
    font-family: fontThree;
    src: url(assets/font3.otf);
  }

.signInFront{
  width: 20vh;
  height: 20vh;
  line-height: 20vh;
  text-align: center;
  border-style: solid;
  border-color: rgba(51,51,51,1);
  border-radius: 50%;
  position: absolute;
  left: 25vw;
  color: rgba(240,240,240,1);
  font-size: 6vh;
  top: 10vh;
  font-family: fontTwo;
}
.signUpFront{
  width: 20vh;
  height: 20vh;
  line-height: 20vh;
  text-align: center;
  border-style: solid;
  border-color: rgba(51,51,51,1);
  border-radius: 50%;
  position: absolute;
  right: 25vw;
  color: rgba(240,240,240,1);
  font-size: 6vh;
  top: 10vh;
  font-family: fontTwo;
}
.frontText{
  width: 100vw;
  position: absolute;
  left: 0vw;
  text-align: center;
  top: 40vh;
  font-size: 15vh;
  color: rgba(240,240,240,1);
  font-family: fontThree;
}
.circle{
  position: absolute;
  left: 0vh;
  top: 0vh;
  width: 20vh;
  height: 20vh;
  stroke-width: 2;
  stroke-dasharray: 15vh;
  fill: none;
  stroke: rgba(240,240,240,1);
  transition: all .5s;
  stroke-linecap: round;
}
.circle svg{
  width: 100%;
  height: 100%;
}
.circle:hover{
  stroke-width: 5;
  transition: all .5s;
  stroke-dasharray: 7vh;
}

.footer{
  position: fixed;
  bottom: 0px;
  width: 100vw;
  text-align: center;
  background-color: rgba(150,100,100,1);
}
.footer a{
  color: white;
  text-decoration: none;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

</style>
