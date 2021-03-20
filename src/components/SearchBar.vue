<template>
	<div class="search-bar">
		<input type="text" placeholder="Search For The IP Address You Want!">
		<button class="search-button"> 
			<img src="../assets/icon-arrow.svg">
		</button>
	</div>
</template>

<script>
export default {
	name: 'SearchBar',
	props: {
		placeHolder: String
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.search-bar{
	
	margin: 0 auto;
	display: grid;
	width:600px;
	grid-template-columns: 90% 10%;
	border-radius: 50%;
}

.search-bar input[type=text] {
	margin: 0;
	min-width: 495px;
	border-radius: 1em 0em 0em 1em;
	border: none;
	padding: 20px;
	color: #333;
	font-weight: bold;
	
}
.search-bar input::placeholder {
  color: #aaa;
  font-weight: normal;
}

.search-button{
	margin: 0;
	padding: 20px 10px;
	border-radius: 0em 1em 1em 0em;
	align-items: center;
	align-self: center;
	align-content: center;
	background-color: #111;
	border: none;
}

.search-button:hover {background-color: #262926}

</style>
