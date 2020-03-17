<template>
	<div class="hello">
		<h1>Welcome to Vue intro</h1>
		<div v-bind:class="myClass">
			The value is {{ count }}
		</div>
		<button @click="myClass = 'unicorn'">Set color to BLUE</button>
		<button @click="myClass = 'racoon'">Set color to MAGENTA</button>
	</div>
</template>

<script>
export default {
	name: 'HelloWorld',
	props: {
		msg: String
	},
	data: () => ({
		count: 1,
		myClass: 'unicorn'
	})
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* .myClass {
	background-color: green;
} */
.unicorn {
	background-color: lightblue;
}
.racoon {
	background-color: magenta;
}
h3 {
	margin: 40px 0 0;
}
ul {
	list-style-type: none;
	padding: 0;
}
li {
	display: inline-block;
	margin: 0 10px;
}
a {
	color: #42b983;
}
</style>
