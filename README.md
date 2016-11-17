# Website Performance Optimization

The challenge for this project is to optimize an online portfolio for speed! Udacity's [Critical Rendering Path course](https://www.udacity.com/course/ud884) served as a guide to learn different techniques to optimize the critical rendering path and make the page render as quickly as possible.

## Getting started
Download the project repository, [WebsiteOptimizationPortfolio](https://github.com/alexsales/frontend-nanodegree-web-performance-optimization/ "GitHub project repository"). Or see below "How to Complete This Project" for more detailed instructions.


#### Part 1: Optimize PageSpeed Insights Score (index.html)

The goal is to achieve a score of 90% or higher for both Mobile and Desktop when evaluating index.html using [Google Pagespeed Insights](https://developers.google.com/speed/pagespeed/insights/).

The key to getting a higher score is to reduce the number of Critical Rendering Paths as well as the Critical Size of our files.

**Optimizations made:**
* Resize pizza image
* Remove render-blocking JS: add async attribute to google analytics
* Optimize CSS delivery: inline all the css and avoid external resources
* Move `<script>` tags to end of html (before closing `<body>` tag);
* Inline CSS

#### Part 2: Optimize Frames per Second (pizza.html)

The goal is to render the page with a consistent frame-rate of 60fps when scrolling. Additionally, when a user resizes the pizzas using the pizza slider, the time to resize must be under 5ms, to give it a smooth transition between the different sizes given.

**Optimizations made (in views/js/main.js):**
* replace all querySelector methods with getElementById
* replace all querySelectorAll methods with getElementsByClassName
* remove determineDX function due to its complex and unnecessary computations
* changePizzaSizes function: determined 3 possible pizza widths(%) and used these in the for loop when it iterates thru all the pizzas
* declare variables outside of loops to improve performance
* dynamically calculate the number of pizzas needed to fill the screen
* implemented a requestAnimationFrame method for smooth scrolling


## How to Complete This Project (Project requirements from Udacity)

To get started, check out the [repository](https://github.com/udacity/frontend-nanodegree-mobile-portfolio) and inspect the code.

### Getting started

#### Part 1: Optimize PageSpeed Insights score for index.html

Some useful tips to help you get started:

1. Check out the [repository](https://github.com/udacity/frontend-nanodegree-mobile-portfolio)
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to the top-level of your project directory to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ./ngrok http 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)

Profile, optimize, measure... and then lather, rinse, and repeat. Good luck!

#### Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher. You will find instructive comments in main.js.

You might find the FPS Counter/HUD Display useful in Chrome developer tools described here: [Chrome Dev Tools tips-and-tricks](https://developer.chrome.com/devtools/docs/tips-and-tricks).

### Helpful Links for Further Optimization (from Udacity)
* [Optimizing Performance](https://developers.google.com/web/fundamentals/performance/ "web performance")
* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")
* [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "optimize the crp!")
* [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "render blocking css")
* [Optimizing JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html "javascript")
* [Measuring with Navigation Timing](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html "nav timing api"). We didn't cover the Navigation Timing API in the first two lessons but it's an incredibly useful tool for automated page profiling. I highly recommend reading.
* [The fewer the downloads, the better](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html)
* [Reduce the size of text](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html)
* [Optimize images](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html)
* [HTTP caching](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html)

### Customization with Bootstrap
The portfolio was built on Twitter's [Bootstrap](http://getbootstrap.com/) framework. All custom styles are in `dist/css/portfolio.css` in the portfolio repo.

* [Bootstrap's CSS Classes](http://getbootstrap.com/css/)
* [Bootstrap's Components](http://getbootstrap.com/components/)
