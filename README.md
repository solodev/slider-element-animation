# Slider Element Animation
Adding animation to elements in your slick slider creates an impressive and dynamic digital experience. [Solodev](https://www.solodev.com/) demonstrates how to accomplish this using [animate.css by Daniel Eden](https://daneden.github.io/animate.css/) in combination with [Slick Slider by Ken Wheeler](http://kenwheeler.github.io/slick/).

## Tutorial

For a detailed tutorial regarding the animation, view Solodev's [Adding Animation to your Hero Slider using animate.css](https://www.solodev.com/blog/web-design/code-examples/adding-animation-to-your-hero-slider-using-animate.css.stml) article.

## Demo

Check out a working example on [JSFiddle](https://jsfiddle.net/solodev/qszmrx2n/).

## HTML

The basic HTML markup for a single slide is as follows:
```
<div class="ct-header tablex item" data-background="images/slide1.jpg">
	<div class="ct-u-display-tablex">
		<div class="inner">
			<div class="container">
				<div class="row">
					<div class="col-md-8 col-lg-6 slider-inner">
						<h1 class="big animated">Big Data. Realtime Insight.</h1>
						<p class="animated">Leverage your data and improve marketing and sales ROI.</p>
						<a class="btn btn-transparent btn-lg text-uppercase animated" href="">Learn More</a>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>
```

Of particular importance is the class "animated" which is used as the identifier for the accompanying JavaScript to add additional classes as the animation is activated.

## CSS

All CSS is included in animated-slider.css.

## JavaScript

Necessary JavaScript for Slick Slider is contained in "animated-slider.js". Additionally, the following JavaScript needs to be initiated on page load: 

```
$(document).ready(function(){			
	$('.ct-slick-homepage').on('init', function(event, slick){
		$('.animated').addClass('activate fadeInUp');
	});		

	$('.ct-slick-homepage').slick({
		autoplay: true,
		autoplaySpeed: 3000,
		pauseOnHover: false,
	});			
	
	$('.ct-slick-homepage').on('afterChange', function(event, slick, currentSlide) {
	  $('.animated').removeClass('off');
	  $('.animated').addClass('activate fadeInUp');
	});		

	$('.ct-slick-homepage').on('beforeChange', function(event, slick, currentSlide) {
	  $('.animated').removeClass('activate fadeInUp');
	  $('.animated').addClass('off');
	});
});
```

The above code shows the interaction between the two resources, animate.css and Slick Slider. First, we must give the first slide the "activate" and "fadeInUp" classes so that it works when the page loads. This must be done before the parameters for the slider itself. Lastly, we use Slick Sliders "afterChange" and "beforeChange" functions to add/remove classes which control the animation display.

In this example, we use the "fadeInUp" class, which moves text from the bottom of the slide to its position. For a full list of possible animation classes, view [animate.css on GitHub](https://github.com/daneden/animate.css).

## External Includes

This tutorial includes the following third-party resources:
```
<link href="https://cdnjs.cloudflare.com/ajax/libs/slick-carousel/1.6.0/slick.min.css" rel="stylesheet" type="text/css" />
<link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" rel="stylesheet" />
<link href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.5.2/animate.min.css" rel="stylesheet" />

<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/slick-carousel/1.6.0/slick.min.js" type="text/javascript"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
```

