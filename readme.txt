Instructions for using particles.js as an interactive background.


1) Download the particles.js library from the official website.

https://github.com/VincentGarreau/particles.js/

2) Choose the particles.js theme for your site

https://vincentgarreau.com/particles.js/

Add CSS styling to the particles-js div. Ensure the z-index is lower than other interactive elements on your page.

#particles-js {
	position: fixed;
	top: 0;
	left: 0;
	z-index: -1;
	width: 100%;
	height: 100%;
}


Add JavaScript to load particles.js followed by additional code to pass mouse events to the particles.js canvas.

For example:

(function () {

    // Load particals.js using the configuration file from step 2
    particlesJS.load('particles-js', '../particles.json');


    // Pass mouse events to particles.js canvas.
    document.addEventListener('mousemove', function (e) {

        const canvas = document.querySelector('.particles-js-canvas-el');

        const e1 = new MouseEvent("mousemove", {
            clientX: e.clientX,
            clientY: e.clientY
        });

        canvas.dispatchEvent(e1);        
    });

    document.addEventListener('click', function (e) {

        const canvas = document.querySelector('.particles-js-canvas-el');

        const e1 = new MouseEvent("click", {
            clientX: e.clientX,
            clientY: e.clientY
        });

        canvas.dispatchEvent(e1);
    });

})();
