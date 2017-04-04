<template>
	<div class="test">
		<h1>{{title}}</h1>
		<p v-if="showName">{{user.firstName}}</p>
		<nav>
			<a v-for="item in items">{{item.title}}</a>
		</nav>

		<button v-on:click="greet('greeting')">Greeting</button>
		<input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enter">
		<hr>
		<label>First Name</label><input type="text" v-model="user.firstName">
		<br/>
		<label>Last Name</label><input type="text" v-model="user.lastName">
		<h3>{{fullName}}</h3>

	</div>
</template>

<script>
	export default {
		name: 'test',
		data() {
			return {
				title: 'Hello World',
				user: {
					firstName: 'John',
					lastName: 'Doe'
				},
				showName: true,
				items: [
					{title: 'Item One'},
					{title: 'Item Two'},
					{title: 'Item Three'}
				]
			}
		},
		methods: {
			greet: function(greeting) {
				alert(greeting);
			},
			pressKey: function(e) {
				console.log(e.target.value);
			},
			enter: function() {
				console.log('enter');
			}

		},
		computed: {
			fullName: function() {
				return this.user.firstName + ' ' + this.user.lastName;
			}
		}

	}
</script>

<style scoped>

</style>