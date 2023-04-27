<script>
 	var btns = document.querySelectorAll('.btn');
  var btnWrapper = document.querySelector('.btn-wrapper');
  var menu = document.querySelector('.menu');
  var exp = document.querySelector('.exp');
 	var btnIndis = document.querySelectorAll('.btn-indi');
 	var cursor = document.querySelector('.cursor');
	var infoBtn = document.querySelector('.info-btn');
  var info = document.querySelector('.info-container');
  var close = document.querySelector('.close');
  var rectSVG = document.querySelectorAll('rect');
  var lines = document.querySelectorAll('.line');
  var bgLines = document.querySelectorAll('.bg-lines');
  var cursorLines = document.querySelectorAll('.cursor-line');
  let expState = false;
  let inCount = 0;
  

  var bgLines = document.querySelectorAll('.let-bg');


  
    var activeItem = null;

    var active = false;
if ($(window).width() < 480) {		
    cursor.addEventListener("touchstart", dragStart, false);
    cursor.addEventListener("touchend", dragEnd, false);
    cursor.addEventListener("touchmove", drag, false);

    cursor.addEventListener("mousedown", dragStart, false);
    cursor.addEventListener("mouseup", dragEnd, false);
    cursor.addEventListener("mousemove", drag, false);

    function dragStart(e) {

      if (e.target !== e.currentTarget) {
        active = true;
        activeItem = cursor;

        if (activeItem !== null) {
          if (!activeItem.xOffset) {
            activeItem.xOffset = 0;
          }

          if (!activeItem.yOffset) {
            activeItem.yOffset = 0;
          }

          if (e.type === "touchstart") {
            activeItem.initialX = e.touches[0].clientX - activeItem.xOffset;
            activeItem.initialY = e.touches[0].clientY - activeItem.yOffset;
          } else {
            console.log("doing something!");
            activeItem.initialX = e.clientX - activeItem.xOffset;
            activeItem.initialY = e.clientY - activeItem.yOffset;
          }
        }
      }
    }

    function dragEnd(e) {
      if (activeItem !== null) {
        activeItem.initialX = activeItem.currentX;
        activeItem.initialY = activeItem.currentY;
      }

      active = false;
      activeItem = null;
    }

    function drag(e) {
      if (active) {
        e.preventDefault();
				if(e.type === "touchmove"){

          activeItem.currentX = e.touches[0].clientX - activeItem.initialX;
          activeItem.currentY = e.touches[0].clientY - activeItem.initialY;
        } else {
          activeItem.currentX = e.clientX - activeItem.initialX;
          activeItem.currentY = e.clientY - activeItem.initialY;
        }

        activeItem.xOffset = activeItem.currentX;
        activeItem.yOffset = activeItem.currentY;

        setTranslate(activeItem.currentX, activeItem.currentY, activeItem);
      }
    }

    function setTranslate(xPos, yPos, el) {
      el.style.transform = "translate3d(" + xPos + "px, " + yPos + "px, 0)";
    }}
else{
document.addEventListener('mousemove', function(e){
  var x = e.clientX;
  var y = e.clientY;
  cursor.style.left = x + 'px';
  cursor.style.top = y + 'px';
});
}

infoBtn.addEventListener("click", function (){
  info.style.transform = "translate(-50%,-80vh)";
  info.style.opacity = "1";
  inCount++;
})

close.addEventListener("click", function (){
  info.style.transform = "translate(-50%, 110vh)";
  info.style.opacity = "0";
  inCount--;
})



let aLetter = document.getElementsByClassName('a-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/a-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, aLetter))
let bLetter = document.getElementsByClassName('b-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/b-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, bLetter)) 
  
let cLetter = document.getElementsByClassName('c-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/c-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, cLetter))
  
let dLetter = document.getElementsByClassName('d-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/d-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, dLetter))
  
let eLetter = document.getElementsByClassName('e-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/e-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, eLetter))
  
let fLetter = document.getElementsByClassName('f-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/f-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, fLetter))
  
let gLetter = document.getElementsByClassName('g-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/g-letter-1.txt")
  .then(response => response.text())
  .then(response => createSVG(response, gLetter))
  
let hLetter = document.getElementsByClassName('h-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/h-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, hLetter))
  
let iLetter = document.getElementsByClassName('i-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/i-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, iLetter))

let jLetter = document.getElementsByClassName('j-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/j-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, jLetter))
  
let kLetter = document.getElementsByClassName('k-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/k-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, kLetter))
  
let lLetter = document.getElementsByClassName('l-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/l-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, lLetter))
  
let mLetter = document.getElementsByClassName('m-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/m-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, mLetter))  
  
 let nLetter = document.getElementsByClassName('n-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/n-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, nLetter))  
  
 let oLetter = document.getElementsByClassName('o-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/o-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, oLetter)) 
  
let pLetter = document.getElementsByClassName('p-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/p-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, pLetter))  
 let qLetter = document.getElementsByClassName('q-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/q-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, qLetter))  
 let rLetter = document.getElementsByClassName('r-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/r-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, rLetter)) 

let sLetter = document.getElementsByClassName('s-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/s-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, sLetter))
  
let tLetter = document.getElementsByClassName('t-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/t-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, tLetter))
  
let uLetter = document.getElementsByClassName('u-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/u-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, uLetter))  
  
 let vLetter = document.getElementsByClassName('v-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/v-letter-1.txt")
  .then(response => response.text())
  .then(response => createSVG(response, vLetter))  
  
 let wLetter = document.getElementsByClassName('w-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/w-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, wLetter)) 
  
let xLetter = document.getElementsByClassName('x-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/x-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, xLetter))  
  
 let yLetter = document.getElementsByClassName('y-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/y-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, yLetter))  
  
 let zLetter = document.getElementsByClassName('z-letter') 
	fetch("https://cdn.jsdelivr.net/gh/thuytrann/twistedgraphene/z-letter.txt")
  .then(response => response.text())
  .then(response => createSVG(response, zLetter)) 

  
function createSVG(response, letter){
  let SVGElement = `
    ${response}
   `
   for(const div of letter){
   div.innerHTML = SVGElement
   }
}


btnIndis.forEach((item, index) =>{
	item.addEventListener("click",  () => {
  		if (item.classList.contains('btn-clicked')){
      	item.classList.remove('btn-clicked');
        if (index == 0){	
      		var units = document.querySelectorAll('rect');
          units.forEach(item =>{
          	item.style.rx = "0";
          	item.style.ry = "0";
          })
          document.querySelector('.rnd-btn').classList.remove('spe-clicked');
      	}
      	else if(index == 1){
      		var units = document.querySelectorAll('rect');
          units.forEach(item =>{
          	item.style.height = "14";
          })
          document.querySelector('.stretch').classList.remove('spe-clicked');
      	}
      	else if(index == 2){
      		lines.forEach(item =>{
        		item.style.background = '#D9D9D9';
        	})
          bgLines.forEach(item =>{
          	item.style.background = '#1E1E1E';
          })
          cursorLines.forEach(item =>{
          	item.style.background = '#595959';
          })
      	document.querySelector('.clr-btn').style.background ='linear-gradient(180deg, #f8fe01, #c94013 87%)'
      	}
        else if(index == 3){
        	document.querySelector('.container').classList.remove('filter');
          document.querySelector('.cursor').classList.remove('filter');
          document.querySelector('#svgInternalID').style.fill = "#1e1e1e";
        }
      }
      else {
      	item.classList.add('btn-clicked');
      	if (index == 0){
          var units = document.querySelectorAll('rect');
        	console.log(units);
          units.forEach(item =>{
          	item.style.rx = "20";
          	item.style.ry = "20";
          })
          document.querySelector('.rnd-btn').classList.add('spe-clicked');
      	}
      	else if(index == 1){
     			var units = document.querySelectorAll('rect');
          units.forEach(item =>{
          	item.style.height = "24";
          })
          document.querySelector('.stretch').classList.add('spe-clicked');
      	}
      	else if(index == 2){
      		lines.forEach(item =>{
        		item.style.background = '#c94013';
        	})
          bgLines.forEach(item =>{
          	item.style.background = '#f8fe01';
          })
          cursorLines.forEach(item =>{
          	item.style.background = '#E8EC36';
          })
      		document.querySelector('.clr-btn').style.background ='linear-gradient(180deg, #D9D9D9, #1E1E1E 87%)';
      	}
        else if(index == 3){
        	document.querySelector('.container').classList.add('filter');
          document.querySelector('.cursor').classList.add('filter');
         document.querySelector('#svgInternalID').style.fill = "white";
        }
      }
  });
})
</script>
