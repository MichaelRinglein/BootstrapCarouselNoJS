# BootstrapCarouselNoJS
The Bootstrap Carousel with the collapse functionality but without the Bootstrap.js or jQuery.js (or other external JS libraries)

[Life example](https://dev.strawanzer.online/bootstrap/carousel.html)

## Why this project?
The carousel is part of a series of animation I make for a client. Those animations are loaded into already existing websites.

Therefore the carousel needs to work without any external JS library (like Bootstrap.js or jQuery) to avoid any possible conflicts between different loaded Javascript libraries. Just like the accordion which is also in my Github.

## How it works
I deleted ```data-ride="carousel"``` and the ```href="#carouselExampleControls"``` from the HTML tags since we don't need those anymore.

Then I added ```onclick="prevSlide()"``` and ```onclick="nextSlide()"``` to the controls.

The ```prevSlide()"``` and ```nextSlide()"``` decrement or increment the integer ```currentSlide``` and pass ```currentSlide``` to the function ```goToSlide()```.

```goToSlide()``` selects all available slides and sets all of them to not active (by simply removing the active class of Bootstrap).

In order to start again at 0 after having passed the last slide we take the modulo ```currentSlide = (n+slides.length)%slides.length;```	 

The then resulting current selected slide ```currentSlide``` is the only one set to active.
