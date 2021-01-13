<template>
	<transition name="slide">
		<div v-show="visible">
        index:{{index}} 
       
        <slot></slot>
		
	</div>
	</transition>
</template>

<script>
	export default{

		data(){

			return{
				index:1,
			}
		},
		computed:{
			visible(){
			  return this.index === this.$parent.index
			}
		}
		

	};
</script>

<style>
	.slide-enter-active{
   animation : slideIn 1s;
	}

	@keyframes slideIn{
		from {transform:translateX(90%);}
		to{transform:translateX(0);}
	}
</style>