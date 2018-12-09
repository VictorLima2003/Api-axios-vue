<template>
	<div>
		<h1>Posts</h1>
		<button @click="getPosts">Get Posts</button>
		<ul>
			<li v-for="post in posts">{{ post.title }}</li>
		</ul>
	</div>	
</template>


<script>
import axios from 'axios';	

export default {
  name: 'Dados',
  data: () => ({
  	posts: [],
  }),

  methods: {
  	getPosts () {
  		axios.get('https://jsonplaceholder.typicode.com/posts').then(response => {
  			this.posts = response.data;
  		});
  	}
  }


}
	
</script>


<style>
	
</style>