<html lang="en">
  
<head>
  <meta charset="utf-8">
  <title>Welcome Spider</title>
  <meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1, maximum-scale=1">
  
  <link href=".style.css" rel="stylesheet" type="text/css">
  
  <!-- Link Swiper's CSS -->
  <link rel="stylesheet" href="https://unpkg.com/swiper/css/swiper.css">
  <link rel="stylesheet" href="https://unpkg.com/swiper/css/swiper.min.css">

  <script src="https://unpkg.com/swiper/js/swiper.js"></script>
  <script src="https://unpkg.com/swiper/js/swiper.min.js"></script>
  
  <script src="./spiders.js"></script>
  <script src="./jquery.min.js"></script>
  
  <script type="text/javascript" src="./script.js"></script>

  <!-- Demo styles -->
  <style>
    body {
      background: #000000;
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
  
  <canvas id="spiders" class="hidden-xs" width="781" height="977"></canvas>

  
</body>
</html>
