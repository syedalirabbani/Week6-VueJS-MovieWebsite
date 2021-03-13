<template>
  <div class="detail">
    <h1>This is a detail page. My name is {{name}}. This is the page for {{movieId}}</h1>
  </div>
</template>

<script>
	
	export default {
		name:"detail",
		data(){
			return{
				name:"ali",
				movieId:this.$route.params.movieId
			}
		},
		mounted(){
			//bila page dibuka pertama kali, lakukan ini
			console.log('hello')
		}

}

</script>