<html lang="en">
  
<head>
  <meta charset="utf-8">
  <title>Swiper demo</title>
  <meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1, maximum-scale=1">

  <!-- Link Swiper's CSS -->
  <link rel="stylesheet" href="https://unpkg.com/swiper/css/swiper.css">
  <link rel="stylesheet" href="https://unpkg.com/swiper/css/swiper.min.css">

  <script src="https://unpkg.com/swiper/js/swiper.js"></script>
  <script src="https://unpkg.com/swiper/js/swiper.min.js"></script>

  <!-- Demo styles -->
  <style>
    body {
      background: #fff;
      font-family: Helvetica Neue, Helvetica, Arial, sans-serif;
      font-size: 14px;
      color:#000;
      margin: 0;
      padding: 0;
     
    }
    .swiper-container {
      width: 100%;
      padding-top: 50px;
      padding-bottom: 50px;
    }
    .swiper-slide {
      background-position: center;
      background-size: cover;
      width: 300px;
      height: 300px;

    }
  </style>
</head>
<body>
  <canvas id="canvas">No HTML5 canvas support.</canvas>
  <!-- Swiper -->
  <div class="swiper-container">
    <div class="swiper-wrapper">
      <div class="swiper-slide" style="background-image:url(./images/nature-1.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-2.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-3.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-4.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-5.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-6.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-7.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-8.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-9.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-1.jpg0)"></div>
    </div>
    <!-- Add Pagination -->
    <div class="swiper-pagination"></div>
  </div>

  <!-- Swiper JS -->
  <script src="../package/js/swiper.min.js"></script>

 <!-- Initialize Swiper -->
  <script>
    var swiper = new Swiper('.swiper-container', {
      effect: 'coverflow',
      grabCursor: true,
      centeredSlides: true,
      slidesPerView: 'auto',
      coverflowEffect: {
        rotate: 50,
        stretch: 0,
        depth: 100,
        modifier: 1,
        slideShadows : true,
      },
      pagination: {
        el: '.swiper-pagination',
      },
    });
  </script>

<div class="swiper-container">
    <div class="swiper-wrapper">
      <div class="swiper-slide" style="background-image:url(./images/nature-1.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-2.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-3.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-4.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-5.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-6.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-7.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-8.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-9.jpg)"></div>
      <div class="swiper-slide" style="background-image:url(./images/nature-1.jpg0)"></div>
    </div>
    <!-- Add Pagination -->
    <div class="swiper-pagination"></div>
  </div>

  <!-- Swiper JS -->
  <script src="../package/js/swiper.min.js"></script>
  
   <script>  
     var mySwiper = new Swiper('.swiper-container', {
     autoplay: {
     delay: 5000,
     },
     pagination: {
        el: '.swiper-pagination',
     });
  </script>

 (function() {
  console.clear();
  var stage = new PIXI.Stage();
  var renderer = PIXI.autoDetectRecommendedRenderer(window.innerWidth, window.innerHeight, {view: document.getElementById("canvas"), transparent: true}
  );
  
  var starTexture = PIXI.Texture.fromImage("https://s3-us-west-2.amazonaws.com/s.cdpn.io/167451/Feedbin-Icon-star.svg");
  
  var colours = [
    0x3498db,  // Blue
    0x9b59b6,  // Purple
    //0xf1c40f,  // Yellow
    //0xd35400,  // Orange
    0xfA2323   // Red
  ];
  
  var starPool = [];
  var starsInUse = [];
  for (var i=0; i<100; i++) {
    var star = new PIXI.Sprite(starTexture);
    star.anchor.x = star.anchor.y = 0.5;
    star.visible = false;
    star.scaleDecay = 0;
    star.alphaDecay = 0;
    star.speed = 0;
    star.velocity = {
      x: 0,
      y: 0
    };
    starPool[i] = star;
    stage.addChild(star);
  }
  
  var spawn = function(x, y) {
    var star = starPool.splice(0, 1)[0];
    star.tint = colours[Math.floor(Math.random() * colours.length)];
    star.scale.x = star.scale.y = (Math.random() * 0.8) + 0.2;
    star.scaleDecay = (Math.random() * 0.05) + 0.05;
    star.alpha = (Math.random() * 0.2) + 0.8;
    star.alphaDecay = (Math.random() * 2) + 1;
    star.rotation = 2 * Math.random() * Math.PI;
    star.x = Math.cos(star.rotation) * 10 + x;
    star.y = Math.sin(star.rotation) * 10 + y;
    star.speed = (Math.random() * 30) + 20;
    star.velocity.x = star.speed * Math.cos(star.rotation);
    star.velocity.y = star.speed * Math.sin(star.rotation);
    star.visible = true;
    starsInUse.push(star);
  };
  
  var updateStars = function(delta) {
    for (var i=0; i<starsInUse.length; i++) {
      var star = starsInUse[i];
      if (star.visible) {
        star.alpha -= star.alphaDecay * delta;
        star.scale.x -= star.scaleDecay * delta;
        star.scale.y -= star.scaleDecay * delta;
        star.x += star.velocity.x * delta;
        star.y += star.velocity.y * delta;
        
        if (star.alpha < 0 || star.scale.x < 0) {
          star.visible = false;
          starPool.push(starsInUse.splice(i, 1)[0]);
        }
      }
    }
  };

  var lastTime = null;
  var animate = function(timestamp) {
    if (lastTime === null) {
      lastTime = timestamp;
    }
    var delta = (timestamp - lastTime) / 1000;
    lastTime = timestamp;
    
    for (var i=0; i<Math.min(starPool.length, 5); i++) {
      var pos = stage.interactionManager.mouse.global;
      spawn(pos.x, pos.y);      
    }
    updateStars(delta);
    
    renderer.render(stage);
    
    requestAnimationFrame(animate);
  };
  
  requestAnimationFrame(animate);
})();

  
</body>
</html>
