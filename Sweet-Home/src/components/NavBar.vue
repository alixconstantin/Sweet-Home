<script setup>

</script>

<template>

  <nav>

    <div class="nav_name">
     <img class="nav_name_image" src="../images/icon-ramen.png" alt="cat logo"> 
      Alix Constantin
    </div>

    <div class="nav_options">
        <div class="nav_options_option">Works</div>
        <div class="nav_options_option">Posts</div>
        <div class="nav_options_option">Uses</div>
        <div class="nav_options_option"><svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 512 512" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg">
        <path d="M256 32C132.3 32 32 134.9 32 261.7c0 101.5 64.2 187.5 153.2 217.9a17.56 17.56 0 003.8.4c8.3 0 11.5-6.1 11.5-11.4 0-5.5-.2-19.9-.3-39.1a102.4 102.4 0 01-22.6 2.7c-43.1 0-52.9-33.5-52.9-33.5-10.2-26.5-24.9-33.6-24.9-33.6-19.5-13.7-.1-14.1 1.4-14.1h.1c22.5 2 34.3 23.8 34.3 23.8 11.2 19.6 26.2 25.1 39.6 25.1a63 63 0 0025.6-6c2-14.8 7.8-24.9 14.2-30.7-49.7-5.8-102-25.5-102-113.5 0-25.1 8.7-45.6 23-61.6-2.3-5.8-10-29.2 2.2-60.8a18.64 18.64 0 015-.5c8.1 0 26.4 3.1 56.6 24.1a208.21 208.21 0 01112.2 0c30.2-21 48.5-24.1 56.6-24.1a18.64 18.64 0 015 .5c12.2 31.6 4.5 55 2.2 60.8 14.3 16.1 23 36.6 23 61.6 0 88.2-52.4 107.6-102.3 113.3 8 7.1 15.2 21.1 15.2 42.5 0 30.7-.3 55.5-.3 63 0 5.4 3.1 11.5 11.4 11.5a19.35 19.35 0 004-.4C415.9 449.2 480 363.1 480 261.7 480 134.9 379.7 32 256 32z">
        </path></svg> <span class="nav_options_optionWithLogo">Source</span></div>
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
  width: 33px;
  padding-right: 13px;
  margin-bottom: 8px;
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

.nav_options_optionWithLogo {
  margin-left:7.5px;
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
