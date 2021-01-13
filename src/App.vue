<template>
  <div>
    
    <Carousel class="carousel">
    	<CarouselSlide>
    	  first child component inside carousel comp
    	  <img src="./assets/4.jpg" alt="">
    	</CarouselSlide>
    	<CarouselSlide>
    		<img src="./assets/2.jpg" alt="">
    		second child component insided carousel comp
    	</CarouselSlide>
    	
    </Carousel>
  </div>
</template>

<script>
import Carousel from './components/carousels/Carousel.vue';
import CarouselSlide from './components/carousels/CarouselSlide.vue';


export default {
  
  components: {
    
    Carousel,
    CarouselSlide
  }
};
</script>
<style>
	.carousel{
		position: relative;
	}
	.carousel__nav{
		position: absolute;
		padding: 5px 19px;
		border:none;
		top:50%;
		transform: translateY(-50%);
		cursor: pointer;
	}
	.carousel_next{
		right:0;
		background: red;
	}
</style>



