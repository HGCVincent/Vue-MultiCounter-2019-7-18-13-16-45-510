<template>
	<div>
		counterSum:{{totalCount}}
	</div>
</template>

<script>
	export default{
		 props: ['counterSum'],
		 computed:{
		     totalCount(){
		         return this.$store.state.totalCount
			 }
		 }
	}
</script>

<style>
</style>
