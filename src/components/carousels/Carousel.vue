<template>
	<div>
		
		<slot></slot>
		<button class="carousel__nav carousel_next"@click.prevent="next">next</button>
		<button class="carousel__nav carousel_prev"@click.prevent="prev"> prev </button>

		
	</div>
</template>

<script>
	export default{
		data(){
			return{
				index:0,
				slides:[]
			}
		},

		 methods:{
		 	next(){
		 		this.index ++ ;
		 		if(this.index >= this.howManySlides ){
		 		  this.index= 0;
		 		}
		 	},
		 	prev(){
		 		this.index --;
		 		if(this.index <= 0){
		 			this.index = this.howManySlides- 1;
		 		}
		 	}

		 },
		 computed:{

		 	howManySlides(){
		 		return this.slides.length;
		 	}

		 },
		mounted(){
			this.slides= this.$children;
		    this.slides.forEach((slide,i)=>{
                 slide.index = i;
				})
			
		}

	};
</script>

