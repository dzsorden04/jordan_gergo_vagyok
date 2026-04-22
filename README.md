<!DOCTYPE html>
<html lang="hu">
<head>
<meta charset="UTF-8">
<title>Gergely</title>

<!-- Limelight font -->
<link href="https://fonts.googleapis.com/css2?family=Limelight&display=swap" rel="stylesheet">

<style>
body {
    margin: 0;
    background: #c23b22;
    font-family: "Limelight", cursive;
    color: white;
    text-align: center;
    overflow-x: hidden;
    cursor: crosshair;
}

h1 {
    margin-top: 40px;
    font-size: 44px;
    font-weight: normal;
}

a, .box {
    display: block;
    margin: 20px auto;
    font-size: 22px;
    color: white;
    text-decoration: none;
    width: fit-content;
}

.box {
    cursor: pointer;
}

#gallery {
    display: none;
    margin-top: 20px;
}

#gallery img {
    width: 320px;
    margin: 15px;
}

/* onlyfans */
#onlyfans {
    position: relative;
}

/* egér víz effekt */
.trail {
    position: fixed;
    width: 70px;
    height: 70px;
    background: rgba(255,255,255,0.25);
    border-radius: 50%;
    pointer-events: none;
    animation: fade 3.5s forwards;
}

@keyframes fade {
    from {opacity:1;}
    to {opacity:0;}
}
</style>
</head>

<body>

<h1>Jordán Gergely</h1>

<a href="https://www.vinted.hu/member/129409216" target="_blank">
Vinted
</a>

<a href="https://www.instagram.com/tebolyult.asvanykarkoto.fuggo/" target="_blank">
Instagram
</a>

<div class="box" onclick="toggleGallery()">
Munkáim
</div>

<div id="gallery">
    <img src="rajz1.PNG">
    <img src="rajz2.PNG">
</div>

<div class="box" id="onlyfans">
onlyfans
</div>

<script>

// GALÉRIA
function toggleGallery(){
    const g = document.getElementById("gallery");
    g.style.display = (g.style.display === "block") ? "none" : "block";
}

// MENEKÜLŐ ONLYFANS
const of = document.getElementById("onlyfans");

of.addEventListener("mouseover", () => {
    let x = Math.random() * (window.innerWidth - 200);
    let y = Math.random() * (window.innerHeight - 100);

    of.style.position = "absolute";
    of.style.left = x + "px";
    of.style.top = y + "px";
});

// EGÉR VÍZ
document.addEventListener("mousemove", (e) => {
    let d = document.createElement("div");
    d.className = "trail";
    d.style.left = (e.pageX - 35) + "px";
    d.style.top = (e.pageY - 35) + "px";

    document.body.appendChild(d);

    setTimeout(() => d.remove(), 3500);
});

// RANDOM HANG MINDEN KATTINTÁSRA
const sounds = [
    "hang1.waw",
    "hang2.waw",
    "hang3.waw",
    "hang4.ogg"
];

document.addEventListener("click", () => {
    let s = sounds[Math.floor(Math.random() * sounds.length)];
    let audio = new Audio(s);
    audio.play();
});

</script>

</body>
</html>
