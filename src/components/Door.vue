 <template>
     <div class="door-area">

     <div class="image">

     </div>
     <div class="door-frame" :class="{ selected: selected && !open }">
       <Gift v-if="open && hasGift" />

     </div>
     <div class="door" :class="{ open }"
      @click="selected = !selected">

     <div class="number" :class="{ selected }" >{{ number }} </div>

     <div class="knob" :class="{ selected }" @click.stop="open = true"></div>

     <div class="wall">
         <div class="threshold">
             <div class="door">
             </div>
         </div>
     </div>
     </div>
     </div>


 </template>

 <script>
import Gift from './Gift'


 export default {
     name: 'Door',
     components:{ Gift },
     props: {
         number: {},
         hasGift: { type: Boolean }
     },
data: function () {
      return {
          open: false,
          selected: false

      }
   }
 }
 </script>

 <style>
 :root {
     --door-border: 5px  black;
     --selected-border: 5px solid #00ffff;

 }

 .door-area {

     position: relative;
     height: 295px;
     width: 170px;
     border-bottom: 10px solid #E31515 ;
     animation: blink 1s;
     animation-iteration-count: 1000;

     background-image:url("../images/Wood.png");

     margin-bottom: 20px;
     font-size:3rem;
     -webkit-text-stroke: 1px black;
      color: white;
      text-shadow:
          2px  2px 0 #000,
         -1px -1px 0 #000,
          1px -1px 0 #000,
         -1px  1px 0 #000,
          1px  1px 0 #000;
     display: flex;
     justify-content:center;

 }

 .alerts-border {
    border: 1px solid;
    animation: blink 1s;
    animation-iteration-count: 3;
}

@keyframes blink { 50% { border-color: #FFFF00; }  }



 .door-frame {

     position:absolute;
     height: 295px;
     width: 170px;
 border-left: var(--door-border);
     border-top: var(--door-border);
     border-right: var(--door-border);
 display: flex;
     justify-content: center;
     align-items: flex-end;


 }

 .door {
     position: absolute;
     top: 5px;
     width: 170px;
     height: 295px;
     display: flex;
     flex-direction: column;
     align-items: center;
     padding: 20px;


 }

 .door .knob {
     height: 45px;
     width: 47px;
     border-radius: 10px;
     background-image: url("../images/P.png");
     align-self: flex-start;
     margin-top: 30px;


 }
 .door-frame.selected {

    border-left: var(--selected-border) ;
    border-top: var(--selected-border);
    border-right: var(--selected-border);
    background-image: url("https://media.giphy.com/media/jTZVegIrdLCCY/giphy.gif");
    width: 170px;
    height: 295px;
    background-repeat: space;


 }

 .door > .number.selected {
 color: yellow ;

 }
 .door > .knob.selected {

   background-color: yellow;
 }

.door.open {
width: 170px;
height: 295px;
margin: auto;
background-image: url("https://media.giphy.com/media/cMso9wDwqSy3e/giphy.gif");

}

 .door.open .knob {
 display: none;


 }



 .door.open .number {
 display:none;

 }





 </style>
