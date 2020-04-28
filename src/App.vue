<template>
    <div id="app">
    <h1> <div class="container">
  <div class="text">
    <span class="letter m">M</span>
    <span class="letter o">O</span>
    <span class="letter n">N</span>
    <span class="letter t">T</span>
    <span class="letter y">Y</span>
    <br>
    <span class="letter h">H</span>
    <span class="letter a">A</span>
    <span class="letter l">L</span>
     <span class="letter l2">L</span>


  </div>
</div></h1>

    <div class="form">
  <div v-if="!started">
    <label for="portsAmount">How many doors? </label><br><br>
    <input type="text" id="portsAmount" size="3"
      v-model.number="portsAmount">

    </div> <br>

    <div v-if="!started">
<label for="selectedPort">Choose winning door<div class = "headers">




</div></label>
<br>
<input type="text" id="selectedPort" size="3"
v-model.number="selectedPort">
       </div>


<br>
       <div class="wrap">
       <button v-if="!started" @click="started = true"> start</button>
       <button v-if="started" @click="started=false"> restart</button>
       </div>
    </div>

    <div class="doors" v-if="started">
      <div v-for="i in  portsAmount" :key="i">
      <Door :hasGift="i === selectedPort" :number="i" />
</div>
    </div>
</div>
</template>

<script>
import Door from  './components/Door'

export default {
    name: 'App',
  components: {Door},
    data: function() {
    return {
    started:false,
    portsAmount: 3,
    selectedPort: null
      }
    }

}
</script>

<style>
* {
    box-sizing: border-box;
    font-family: "Monteserrat", sans-serif;
}

body {

    background-image: url('./images/Wall.png');


  background-color: #000;
  font-family:  cursive;
}

#app {
    display: flex;
    flex-direction:column;
    align-items: center;
}
#app h1 {
    border: 1px solid #000;
    background-color: #0004;
    padding: 20px;
    margin-bottom: 60px;
}

.form {
font-family: "Monteserrat", sans-serif;
color: #fff01f;
display: flex;
flex-direction: column;
justify-content: right;
align-items: center;
margin-bottom: 40px;
color: white;
-webkit-animation: h2 0.35s infinite;
animation: h2 0.35s infinite;


}

.form, .form input, .form button {
margin-bottom: 10px;
font-size: 2rem;
text-align: center;

}

.doors {

align-self: stretch;
display:flex;
justify-content: space-around;
flex-wrap: wrap;
}

button {

position: relative;
  outline: none;
  text-decoration: none;
  border-radius: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  text-transform: uppercase;
  height: 60px;
  width: 210px;
  opacity: 1;
  background: #fffc00;  /* fallback for old browsers */
background: -webkit-linear-gradient(to right, #ffffff, #fffc00);  /* Chrome 10-25, Safari 5.1-6 */
background: linear-gradient(to right, #ffffff, #fffc00); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */





}

.container {

  display: flex;
  align-items: center;
  justify-content: center;
}

.text {
   font-family: verdana;
   text-align: center;
   font-size: 35px;
   color: rgba(255, 240, 31, 1);
   text-shadow: rgb(0, 0, 0) 2px 2px 2px;
}

.text .letter.m {
  animation-delay: 0.3s;
color: rgba(251, 251, 75, 0.92);
text-shadow: rgb(0, 0, 0) 2px 2px 2px;
}

.text .letter.o {
  animation-delay: 0.15s;
  color: rgba(251, 251, 75, 0.92);
  text-shadow: rgb(0, 0, 0) 2px 2px 2px;
}

.text .letter.n {
  animation-delay: 0.4s;
  color: rgba(251, 251, 75, 0.92);
  text-shadow: rgb(0, 0, 0) 2px 2px 2px;
}

.text .letter.t {
  animation-delay: 0.25s;
  color: rgba(251, 251, 75, 0.92);
  text-shadow: rgb(0, 0, 0) 2px 2px 2px;
}

.text .letter.y {
  animation-delay: 0.5s;
  color: rgba(251, 251, 75, 0.92);
  text-shadow: rgb(0, 0, 0) 2px 2px 2px;
}

.text .letter.h {
  animation-delay: 0.5s;
  color: rgba(251, 251, 75, 0.92);
  text-shadow: rgb(0, 0, 0) 2px 2px 2px;
}
.text .letter.a {
  animation-delay: 0.15s;
  color: rgba(251, 251, 75, 0.92);
  text-shadow: rgb(0, 0, 0) 2px 2px 2px;
}
.text .letter.l {
  animation-delay: 0.4s;
  color: rgba(251, 251, 75, 0.92);
  text-shadow: rgb(0, 0, 0) 2px 2px 2px;
}
.text .letter.l2 {
  animation-delay: 0.7s;
  color: rgba(251, 251, 75, 0.92);
  text-shadow: rgb(0, 0, 0) 2px 2px 2px;
}

.text .letter {
  position: relative;
  animation: move 1.85s infinite;
}

@keyframes move {
  0% {
    top: 0;
  }
  50% {
    top: -20px;
  }
  100% {
    top: 0;
  }
}

 h2{
  font-family: 'Monoton', cursive;
  font-size: 40px;
  color: rgba(255, 240, 31, 1);

}

h2 {
font-family:  cursive;
  color: white;
  -webkit-animation: h2 0.35s infinite;
  animation: h2 0.35s infinite;
}

@keyframes h2 {
    0%   {text-shadow: 0 0 6px #FFF;}
    100%  {text-shadow: 0 0 0px #000;}
}

.wrap {
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.button {
  min-width: 300px;
  min-height: 60px;
  font-family: 'Nunito', sans-serif;
  font-size: 22px;
  text-transform: uppercase;
  letter-spacing: 1.3px;
  font-weight: 700;
  color: #313133;
  background: #4FD1C5;
background: linear-gradient(90deg, rgba(129,230,217,1) 0%, rgba(79,209,197,1) 100%);
  border: none;
  border-radius: 1000px;
  box-shadow: 12px 12px 24px rgba(79,209,197,.64);
  transition: all 0.3s ease-in-out 0s;
  cursor: pointer;
  outline: none;
  position: relative;
  padding: 10px;
  }

button::before {
content: '';
  border-radius: 1000px;
  min-width: calc(300px + 12px);
  min-height: calc(60px + 12px);
  border: 6px solid #00FFCB;
  box-shadow: 0 0 60px rgba(0,255,203,.64);
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  opacity: 0;
  transition: all .3s ease-in-out 0s;
}

.button:hover, .button:focus {
  color: #313133;
  transform: translateY(-6px);
}

button:hover::before, button:focus::before {
  opacity: 1;
}

button::after {
  content: '';
  width: 30px; height: 30px;
  border-radius: 100%;
  border: 6px solid ##ffff00;
  position: absolute;
  z-index: -1;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  animation: ring 1.5s infinite;
}

button:hover::after, button:focus::after {
  animation: none;
  display: none;
}

@keyframes ring {
  0% {
    width: 30px;
    height: 30px;
    opacity: 1;
  }
  100% {
    width: 300px;
    height: 300px;
    opacity: 0;
  }
}

</style>
