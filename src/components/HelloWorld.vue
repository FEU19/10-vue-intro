<template>
	<div class="hello">
		<h1>Welcome to Vue intro</h1>
		<div v-bind:class="myClass" v-bind:style="{ 'background-color': myStyle}">
			The value is {{ count }}
		</div>

		<div class="buttons">
			<input type="text" @keyup="handleKeyUp" />
			<button @click="handleClickSetColor">Set color?</button>
			<!-- {{ inputColor }} -->
			<br />

			<button @click="myClass = 'unicorn'">Set color to BLUE</button>
			<button @click="myClass = 'racoon'">Set color to MAGENTA</button>
			<button @click="myClass = 'basilisk'">Set basilisk</button>
		</div>
		{{ myClass }}

		<div v-if="myClass == 'racoon'">
			Only visible if we have a racoon
		</div>
		<div v-else-if="myClass == 'unicorn'">
			Only visible if we have a unicorn
		</div>
		<div v-else>
			Something else?
		</div>
		<div v-show="myClass == 'racoon'">
			Also only visible if we have a racoon
		</div>

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
		myClass: 'unicorn',
		myStyle: '',
		inputColor: ''
	}),
	methods: {
		handleKeyUp(event) {
			console.log('handleKeyUp event=', event);
			this.inputColor = event.target.value;
		},
		handleClickSetColor() {
			this.myStyle = this.inputColor;
		}
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* .myClass {
	background-color: green;
} */
.em-small {
	height: 1em;
}
.em-large {
	height: 2em;
}
.em-small, .em-large {
	border: 1px solid black;
	width: 3.5em;
}
.buttons {
	margin-top: 2rem;
}
.unicorn {
	background-color: lightblue;
}
.racoon {
	background-color: magenta;
}
.basilisk {
	background-color: gray;
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
