/* CURSOR FOLLOW GLOW */
const glow = document.querySelector(".cursor-glow");

if (glow) {
    document.addEventListener("mousemove", (e) => {
        glow.style.left = e.clientX + "px";
        glow.style.top = e.clientY + "px";
        glow.style.opacity = "1";
    });

    document.addEventListener("mouseleave", () => {
        glow.style.opacity = "0";
    });
}

/* CLUES */
const clues = document.querySelectorAll(".hidden-clue");

document.addEventListener("mousemove", (e) => {
    clues.forEach(clue => {
        const rect = clue.getBoundingClientRect();
        const dx = e.clientX - (rect.left + rect.width / 2);
        const dy = e.clientY - (rect.top + rect.height / 2);
        const distance = Math.sqrt(dx * dx + dy * dy);

        clue.style.opacity = distance < 120 ? "1" : "0";
    });
});

/* BLOOD */
const bloodMarks = document.querySelectorAll(".blood-mark");

document.addEventListener("mousemove", (e) => {
    bloodMarks.forEach(mark => {
        const rect = mark.getBoundingClientRect();
        const dx = e.clientX - (rect.left + rect.width / 2);
        const dy = e.clientY - (rect.top + rect.height / 2);
        const distance = Math.sqrt(dx * dx + dy * dy);

        mark.style.opacity = distance < 140 ? "0.85" : "0";
    });
});

/* Dynamic */
document.addEventListener("mousemove", (e) => {
    const x = (e.clientX / window.innerWidth - 0.5) * 8;
    const y = (e.clientY / window.innerHeight - 0.5) * 8;

    document.querySelectorAll(".container, .menu-image-wrapper, .top-left")
        .forEach(el => {
            el.style.transform = `translate(${x}px, ${y}px)`;
        });
});


/* LOOPING TYPING EFFECT */
const typedText = document.getElementById("typed");

if (typedText) {
    const headline = "Ready to play detective?";
    let index = 0;
    let isDeleting = false;

    function typeLoop() {
        if (!isDeleting) {
            typedText.textContent = headline.substring(0, index + 1);
            index++;
            if (index === headline.length) {
                setTimeout(() => isDeleting = true, 1500);
            }
        } else {
            typedText.textContent = headline.substring(0, index - 1);
            index--;
            if (index === 0) isDeleting = false;
        }
        setTimeout(typeLoop, isDeleting ? 50 : 90);
    }

    setTimeout(typeLoop, 2300);
}

/* CREATE COMING SOON RINGS */
function createRing(id) {
    const ring = document.getElementById(id);
    const text = ring.innerText;
    ring.innerHTML = "";

    const radius = 120;
    const chars = text.split("");
    const step = 360 / chars.length;

    chars.forEach((char, i) => {
        const span = document.createElement("span");
        span.innerText = char;
        span.style.transform = `rotateY(${step * i}deg) translateZ(${radius}px)`;
        ring.appendChild(span);
    });
}

if (document.getElementById("ringTextX")) {
    createRing("ringTextX");
    createRing("ringTextY");
}

/* HORROR FLICKER */
setInterval(() => {
    document.body.style.filter =
        Math.random() > 0.97 ? "brightness(0.9)" : "brightness(1)";
}, 140);

const menuBtn = document.getElementById("menuBtn");
if (menuBtn) {
    menuBtn.addEventListener("click", () => {
        document.body.style.opacity = "0";
        setTimeout(() => {
            window.location.href = "menu.html";
        }, 600);
    });
}

const menuItems = [
    { src: "Black Gulaman.jpg", title: "Black Gulaman" },
    { src: "Dynamite.jpg", title: "Dynamite" },
    { src: "Indo mie.jpg", title: "Indo mie" },
    { src: "Walking Chips.jpg", title: "Walking Chips" }
];

let current = 0;

const slide = document.getElementById("slide");
const menuImage = document.getElementById("menuImage");
const menuTitle = document.getElementById("menuTitle");

function changeSlide(direction) {
    slide.classList.remove("active");
    slide.classList.add(direction === "next" ? "exit-left" : "exit-right");

    setTimeout(() => {
        slide.className = "slide";
        current =
            direction === "next"
                ? (current + 1) % menuItems.length
                : (current - 1 + menuItems.length) % menuItems.length;

        menuImage.src = menuItems[current].src;
        menuImage.alt = menuItems[current].title;
        menuTitle.textContent = menuItems[current].title;

        slide.classList.add(direction === "next" ? "enter-right" : "enter-left");

        requestAnimationFrame(() => {
            slide.classList.remove("enter-right", "enter-left");
            slide.classList.add("active");
        });
    }, 600);
}

document.getElementById("next").addEventListener("click", () => {
    changeSlide("next");
});

document.getElementById("prev").addEventListener("click", () => {
    changeSlide("prev");
});

slide.classList.add("active");
