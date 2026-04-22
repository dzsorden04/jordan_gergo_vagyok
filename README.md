<!DOCTYPE html>
<html lang="hu">
<head>
<meta charset="UTF-8">
<title>Jordán Gergely</title>

<style>
body {
    margin: 0;
    background: #8B0000;
    font-family: "Times New Roman", serif;
    color: white;
    text-align: center;
    overflow-x: hidden;
}

h1 {
    margin-top: 40px;
    font-size: 32px;
    font-weight: normal;
}

.container {
    margin-top: 50px;
}

.box {
    display: inline-block;
    width: 220px;
    height: 120px;
    margin: 20px;
    background: rgba(255,255,255,0.15);
    border: 2px solid white;
    line-height: 120px;
    font-size: 22px;
    text-decoration: none;
    color: white;
    transition: 0.3s;
    cursor: pointer;
}

.box:hover {
    background: rgba(255,255,255,0.3);
}

#onlyfans {
    position: relative;
}

#gallery {
    display: none;
    margin-top: 40px;
}

#gallery img {
    width: 400px;
    margin: 20px;
    border: 2px solid white;
}

/* egér trail */
.trail {
    position: fixed;
    width: 70px;
    height: 70px;
    background: rgba(255, 180, 180, 0.35);
    border-radius: 50%;
    pointer-events: none;
    animation: fadeOut 4s forwards;
}

@keyframes fadeOut {
    from {opacity:1;}
    to {opacity:0;}
}
</style>
</head>

<body>

<h1>Jordán Gergely</h1>

<div class="container">

<a class="box"
href="https://www.instagram.com/tebolyult.asvanykarkoto.fuggo/"
target="_blank">
Instagram
</a>

<a class="box"
href="https://www.vinted.hu/member/129409216"
target="_blank">
Vinted
</a>

<div class="box" onclick="toggleGallery()">
Fotók
</div>

<div class="box" id="onlyfans">
OnlyFans
</div>

</div>

<div id="gallery">
    <h2>Munkáim</h2>

    <img src="rajz1.PNG">
    <img src="rajz2.PNG">
</div>

<script>

// Fotó galéria nyitás/zárás
function toggleGallery() {
    const gallery = document.getElementById("gallery");

    if (gallery.style.display === "none" || gallery.style.display === "") {
        gallery.style.display = "block";
    } else {
        gallery.style.display = "none";
    }
}

// Menekülő onlyfans
const onlyfans = document.getElementById("onlyfans");

onlyfans.addEventListener("mouseover", function() {
    let x = Math.random() * (window.innerWidth - 250);
    let y = Math.random() * (window.innerHeight - 150);

    onlyfans.style.position = "absolute";
    onlyfans.style.left = x + "px";
    onlyfans.style.top = y + "px";
});

// Egér utáni vízszerű trail
document.addEventListener("mousemove", function(e) {
    let trail = document.createElement("div");

    trail.className = "trail";
    trail.style.left = (e.pageX - 35) + "px";
    trail.style.top = (e.pageY - 35) + "px";

    document.body.appendChild(trail);

    setTimeout(() => {
        trail.remove();
    }, 4000);
});

// Random hang kattintásra
const sounds = [
    "hang1.waw",
    "hang2.waw",
    "hang3.waw",
    "hang4.ogg"
];

document.addEventListener("click", function() {
    let randomSound =
        sounds[Math.floor(Math.random() * sounds.length)];

    let audio = new Audio(randomSound);
    audio.play();
});

</script>

</body>
</html>
hang4.ogg

Ha valamelyik név eltér (kisbetű/nagybetű is számít), akkor javítsd a kódban.
