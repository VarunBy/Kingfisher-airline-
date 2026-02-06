# Kingfisher-airline-
A New Idea to Fly
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Kingfisher Airlines – Concept</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

<style>
:root{
  --red:#c8102e;
  --gold:#d4af37;
  --blue:#0a1f44;
  --white:#ffffff;
}

*{margin:0;padding:0;box-sizing:border-box;font-family:Poppins,sans-serif}
body{background:#f8f8f8;color:#222}

/* NAVBAR */
nav{
  position:fixed;top:0;width:100%;
  background:var(--white);
  display:flex;justify-content:space-between;
  padding:15px 30px;z-index:999;
  box-shadow:0 2px 10px rgba(0,0,0,.1)
}
nav h1{color:var(--red)}
nav a{margin-left:20px;text-decoration:none;color:var(--blue);font-weight:500}

/* HERO */
.hero{
  height:100vh;
  background:
    linear-gradient(rgba(0,0,0,.45),rgba(0,0,0,.45)),
    url("https://upload.wikimedia.org/wikipedia/commons/5/5a/Kingfisher_Airlines_A320.jpg") center/cover no-repeat;
  display:flex;align-items:center;justify-content:center;
  text-align:center;color:white;
}
.hero h2{font-size:3rem}
.hero p{margin-top:15px;font-size:1.1rem}
.hero button{
  margin-top:25px;padding:14px 28px;
  border:none;border-radius:30px;
  background:var(--gold);color:black;
  font-weight:600;font-size:1rem;
}

/* SECTION */
section{padding:90px 8%}
.title{text-align:center;margin-bottom:50px}
.title h2{color:var(--red)}

/* AIRCRAFT SCROLL ANIMATION */
.aircraft-scroll{
  position:relative;height:200px;overflow:hidden
}
.aircraft-scroll img{
  position:absolute;width:300px;
  left:-320px;top:40px;
  transition:transform 1.2s ease
}
.aircraft-scroll.active img{
  transform:translateX(120vw)
}

/* DOTTED PATH */
.path{
  margin-top:40px;
  border-top:3px dashed var(--blue);
  position:relative
}
.path::after{
  content:"✈️";position:absolute;
  right:0;top:-18px;font-size:24px
}

/* SEAT SELECTION */
.seats{
  display:grid;
  grid-template-columns:repeat(6,1fr);
  gap:10px;max-width:420px;
  margin:0 auto
}
.seat{
  padding:12px 0;
  background:#ddd;
  text-align:center;
  border-radius:6px;
  cursor:pointer
}
.seat.selected{background:var(--gold)}
.seat.booked{background:#777;color:white;cursor:not-allowed}

/* MAP */
.map iframe{
  width:100%;height:350px;border-radius:12px;border:0
}

/* BOTTOM NAV (MOBILE) */
.bottom-nav{
  position:fixed;bottom:0;width:100%;
  background:var(--white);
  display:flex;justify-content:space-around;
  padding:10px 0;box-shadow:0 -2px 10px rgba(0,0,0,.15)
}
.bottom-nav div{text-align:center;font-size:.8rem;color:var(--blue)}

/* RESPONSIVE */
@media(max-width:768px){
  .hero h2{font-size:2.2rem}
}
</style>
</head>

<body>

<!-- NAV -->
<nav>
  <h1>Kingfisher</h1>
  <div>
    <a href="#boarding">Boarding</a>
    <a href="#seats">Seats</a>
    <a href="#navigation">Navigation</a>
  </div>
</nav>

<!-- HERO -->
<div class="hero">
  <div>
    <h2>Fly The Kingfisher Way</h2>
    <p>Luxury • Comfort • Experience</p>
    <button>View E-Boarding Pass</button>
  </div>
</div>

<!-- AIRCRAFT SCROLL -->
<section>
  <div class="title">
    <h2>Journey Visualization</h2>
    <p>Animated flight path experience</p>
  </div>
  <div class="aircraft-scroll" id="plane">
    <img src="https://upload.wikimedia.org/wikipedia/commons/5/5a/Kingfisher_Airlines_A320.jpg">
  </div>
  <div class="path"></div>
</section>

<!-- SEAT SELECTION -->
<section id="seats">
  <div class="title">
    <h2>Seat Selection</h2>
    <p>Choose your perfect seat</p>
  </div>

  <div class="seats">
    <div class="seat">1A</div>
    <div class="seat">1B</div>
    <div class="seat booked">1C</div>
    <div class="seat">1D</div>
    <div class="seat">1E</div>
    <div class="seat">1F</div>

    <div class="seat">2A</div>
    <div class="seat">2B</div>
    <div class="seat">2C</div>
    <div class="seat booked">2D</div>
    <div class="seat">2E</div>
    <div class="seat">2F</div>
  </div>
</section>

<!-- NAVIGATION -->
<section id="navigation">
  <div class="title">
    <h2>Airport Navigation</h2>
    <p>CSMT → Boarding Gate Directions</p>
  </div>

  <div class="map">
    <iframe 
      src="https://www.google.com/maps?q=CSMT%20Mumbai&output=embed">
    </iframe>
  </div>
</section>

<!-- BOTTOM NAV -->
<div class="bottom-nav">
  <div>🏠<br>Home</div>
  <div>🎫<br>Pass</div>
  <div>🧭<br>Navigate</div>
  <div>🪑<br>Seats</div>
  <div>👤<br>Profile</div>
</div>

<script>
/* Scroll Animation */
window.addEventListener("scroll",()=>{
  const plane=document.getElementById("plane");
  const pos=plane.getBoundingClientRect().top;
  if(pos<window.innerHeight-100){
    plane.classList.add("active");
  }
});

/* Seat Selection */
document.querySelectorAll(".seat").forEach(seat=>{
  seat.addEventListener("click",()=>{
    if(seat.classList.contains("booked"))return;
    seat.classList.toggle("selected");
  });
});
</script>

</body>
</html>#ff000a