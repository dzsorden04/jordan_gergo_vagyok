<!DOCTYPE html>
<html lang="hu">
<head>
<meta charset="UTF-8">
<title>Jordán Gergely</title>

<style>
  body {
    margin: 0;
    font-family: "Times New Roman", Times, serif;
    background: #c23b22;
    color: white;
    text-align: center;
    overflow: hidden;
  }

/* onlyfans */
#onlyfans {
    position: relative;

  h1 {
    margin-top: 50px;
  }

  a {
    color: white;
    font-size: 20px;
    display: block;
    margin: 20px;
    text-decoration: none;
  }

  a:hover {
    text-decoration: underline;
  }

  #gallery {
    display: none;
    margin-top: 20px;
  }

  #gallery img {
    width: 300px;
    margin: 10px;
  }

  canvas {
    position: fixed;
    top: 0;
    left: 0;
    z-index: -1;
  }
</style>
</head>

<body>

<h1>Jordán Gergely</h1>

<a href="https://www.instagram.com/tebolyult.asvanykarkoto.fuggo/" target="_blank">
Instagram
</a>

<a href="https://www.vinted.hu/member/129409216" target="_blank">
Vinted
</a>

<a href="#" onclick="toggleGallery()">Munkáim</a>

<div id="gallery">
  <img src="rajz1.png">
  <img src="rajz2.png">
</div>

<canvas id="trail"></canvas>

<script>
const canvas = document.getElementById("trail");
const ctx = canvas.getContext("2d");

canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

let circles = [];

document.addEventListener("mousemove", (e) => {
  circles.push({
    x: e.clientX,
    y: e.clientY,
    alpha: 1
  });
});

function animate() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);

  for (let i = 0; i < circles.length; i++) {
    let c = circles[i];

    ctx.beginPath();
    ctx.arc(c.x, c.y, 40, 0, Math.PI * 2);
    ctx.fillStyle = "rgba(150, 0, 40," + c.alpha + ")";
    ctx.fill();

    c.alpha -= 0.01;

    if (c.alpha <= 0) {
      circles.splice(i, 1);
      i--;
    }
  }

  requestAnimationFrame(animate);
}

animate();

window.addEventListener("resize", () => {
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;
});

// GALÉRIA
function toggleGallery() {
  const g = document.getElementById("gallery");
  g.style.display = (g.style.display === "block") ? "none" : "block";
}

// HANG MINDEN KATTINTÁSRA (CSAK hang4.ogg)
document.addEventListener("click", () => {
  let audio = new Audio("hang4.ogg");
  audio.play();
});
</script>

</body>
</html>
