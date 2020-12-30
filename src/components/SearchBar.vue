<template>
	<div class="search-box">
		<input 
			type="text"
			name="search-bar" 
			id="" 
			class="search-bar" 
			placeholder="Seach..."
			v-model="query"
			@keypress="fetchWeather" />
	</div>
	
</template>

<script>
	export default {
		name: 'search-bar',
		data() {
			return {
				query: ""
			}
		},

		methods: {
			fetchWeather(input) {
				if(input.key == "Enter") {
					this.$emit('fetch:weather', this.query)
				}
				
			}
		}
	}
</script>

<style scoped>
	body {
		font-family: 'monserrat', sans-serif;
	}

	.search-box {
		width: 100%;
		margin-bottom: 30px;
	}

	.search-box .search-bar {
		display: block;
		width: 100%;
		padding: 15px;

		color: #313131;
		font-size: 20px;

		appearance: none;
		border: none;
		outline: none;
		background: none;

		box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.15);
		background-color: rgba(255, 255, 255, 0.5);
		border-radius: 5px;
	}
</style>