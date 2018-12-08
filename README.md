### Sequence
---
https://github.com/IanLunn/Sequence

```js
$(document).ready(function(){
  var sequence = $("#sequence").sequence().data("sequence");
});

$(document).ready(function(){
  var sequence = $("#sequence").sequence().data("sequence");
  var sequence2 = $("#sequence2").sequence().data("sequence");
});
```

```
bower install sequencejs
npm install sequencejs

$(document).ready(function(){
  var options = {
    autoPlay: true,
    autoPlayDelay: 3000
  }
  var sequence = $("#sequence").sequence(options).data("sequence");
});

$(document).ready(function(){
  var options = {
    autoPlay: true,
    autoPlayDelay: 3000
  }
  var sequence = $("#sequence").sequence(options).data("sequence");
  var sequence2 = $("#sequence2").sequence(options).data("sequence");
});

$(document).ready(function(){
  var options = {
  }
  var options2 = {
    autoPlay: false,
    autoPlayDelay: 5000
  }
  var sequence = $("#sequence").sequence(options).data("sequence");
  var sequence = $("#sequence2").sequence(options2).data("sequence");
});

$(document).ready(function(){
  var options = {
    var options = {
      fallback: {
        theme: "slide",
        speed: 500
      }
    }
  }
  var sequence = $("#sequence").sequence(options).data("sequence");
});

$(document).ready(function(){
  var options = {
    autoPlay: true,
    autoPlayDelay: 3000
  }
  var sequence = $("#sequence").sequence(options).data("sequence");
  sequence.beforeCurrentFrameAnimatesOut = function(){
    alert("Do something before the CURRENT frame animates out");
  };
  sequence.beforeNextFrameAnimatesIn = function(){
    alert("Do something before the NEXT frame animates in");
  };
});

sequence.goTo(3, 1);
sequence.goTo(2, -1);

sequence.pause()
sequence.unpause()
sequence.next()
sequence.prev()
sequence.startAutoPlay(1000);
sequence.stopAutoPlay()
alert(sequence.currentFramID);

var options = {};
var mySequence = undefined;
function initSequence(){
  mySequence = $("#sequence").sequence(options).data("sequence");
  mySequence.afterLoaded = function(){
  }
}
$("#destroy").on('click', function(){
  mySequence.destroy();
  mySequence = undefined;
});
$('#create').on('click', function(){
  initSequence();
});
```

```
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
<script src="scripts/jquery.sequence-min.js"></script>
```

```css
#sequence {
  border: black solid 3px;
  height: 370px;
  margin: 10px auto;
  position: relative;
  width: 450px;
}

#sequence > .sequence-canvas li > * { /* required */
  position: absolute;
}

.info1,
.info2,
.info3 {
  background: #3f7ad6;
  color: white;
  height: 95px;
  padding: 5px;
  width: 95px;
}

.sequence-pagination .current {
  font-weight: bold;
}

.sequence-preloader{
  height: 100%;
  position: absolute;
  width: 100%;
  z-index: 999999;
}
@keyframes preload{
  0%{
    opacity: 1;
  }
  50%{
    opacity: 0;
  }
  100%{
    opacity: 1;
  }
}
```
