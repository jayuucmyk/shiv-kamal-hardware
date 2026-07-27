const galleryImages = document.querySelectorAll(".gallery-grid img");

const lightbox = document.querySelector(".lightbox");

const lightboxImg = document.querySelector(".lightbox-img");

const closeBtn = document.querySelector(".close");

galleryImages.forEach(img=>{

    img.addEventListener("click",()=>{

        lightbox.style.display="flex";

        lightboxImg.src=img.src;

    });

});

closeBtn.addEventListener("click",()=>{

    lightbox.style.display="none";

});

lightbox.addEventListener("click",(e)=>{

    if(e.target===lightbox){

        lightbox.style.display="none";

    }

});

/* Counter Animation */

const counters = document.querySelectorAll(".counter");

counters.forEach(counter => {

    const updateCounter = () => {

        const target = +counter.dataset.target;

        const current = +counter.innerText;

        const increment = Math.ceil(target / 80);

        if(current < target){

            counter.innerText = current + increment;

            setTimeout(updateCounter,25);

        }else{

            counter.innerText = target + "+";

        }

    };

    updateCounter();

});