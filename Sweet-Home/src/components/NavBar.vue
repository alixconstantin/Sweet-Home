<script setup>
</script>

<template>

  <nav>

    <div class="nav_name">
      <img src="../images/animal.png" alt="cat logo">
      Alix Constantin
    </div>

    <div class="nav_options">
        <div class="nav_options_option">Works</div>
        <div class="nav_options_option">Posts</div>
        <div class="nav_options_option">Uses</div>
        <div class="nav_options_option"><img src="../images/github.png" alt=""> Source</div>
    </div>

    <div class="nav_lightMode">
      <div class="nav_lightMode_toggle">
        <img src="../images/sun.png" alt="dark/light mode">

      </div>
    </div>


  </nav>

  <div class="test">

  </div>
</template>



<style >
nav {
  width: 882px;
  height: 56px;
  /*background-color: bisque; */
  display: flex;
  background: #20202380;
  z-index: 2;
  position: fixed;
  backdrop-filter: blur(10px);
}

.nav_name {
  padding-left: 15px;
  color:white;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  background-color: aqua; 
  width: 30%;
  height: 100%;
  font-family: 'M PLUS Rounded 1c', sans-serif;
}

.nav_name img {
  width: 43px;
  padding-right: 6px;
  margin-bottom: 10px;
}


.nav_options {
  background-color: rgb(144, 101, 184);
  height: 100%;
  width: 50%;
  display: flex;
}
.nav_options_option {
  height: 100%;
  width: 25%;
  border: 3px solid red;
  display: flex;
  justify-content: center;
  align-items: center;
  color:white;
}

.nav_options_option img{
width: 20px;
padding:6px;
}


.nav_lightMode {
  background-color: rgb(210, 114, 114);
  height: 100%;
  width: 30%;
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

.nav_lightMode_toggle {
  height: 50px;
  width: 50px;
  background-image: radial-gradient(circle, #fbd38b, #f9cf82, #f8cb7a, #f6c671, #f4c268);
  margin-right: 3px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
}

@keyframes rotation {
  0% {
    transform: rotate(0deg);
    animation-timing-function: ease-out;
  }
  50% {
    transform: rotate(180deg);
    animation-timing-function: linear;
  }
  100% {
    transform: rotate(360deg);
    animation-timing-function: ease-in;
  }
}
.nav_lightMode_toggle:hover > img {
  animation-name: rotation;
  animation-duration: 4s;
  animation-timing-function: ease-in-out;
  animation-iteration-count: infinite;
}
.nav_lightMode_toggle:hover {
  background-image: radial-gradient(circle, #be800b, #f9cf82, #f8cb7a, #f6c671, #f4c268);
}

.nav_lightMode_toggle img {
  width: 23px;
}

.test {
  width: 100%;
  height:30000px;
  background-color: aquamarine;
}
</style>
