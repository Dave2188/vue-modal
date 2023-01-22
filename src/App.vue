<template>
	<h1>{{ title }}</h1>
	<p>Welcome!!!</p>
	<div v-if="showModal">
		<Modal theme="sale" @close="toggleModal">
			<h1>{{ this.header }}</h1>
			<p>{{ this.text }}</p>
			<template v-slot:links>
				<a href="#">Sign up</a>
				--
				<a href="#">Log In</a>
			</template>
		</Modal>
	</div>
	<Modal v-if="showModalTwo" @close="toggleModalTwo" theme="sale">
		<h1>Sign In</h1>
		<p>Please fill out all fields</p>
		<br />
		<template v-slot:userData>
			<fieldset>
				<label for="userName">User Name</label>
				<input type="text" name="userName" />
			</fieldset>
			<br />
			<fieldset>
				<label for="password">Password</label>
				<input type="text" name="Password" />
			</fieldset>
		</template>
	</Modal>

	<button @click="toggleModal">Open Modal</button>
	<button @click="toggleModalTwo">Open Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
	name: "App",
	components: { Modal },
	data() {
		return {
			title: "My First Vue App!!!!",
			header: "Sign up here for a chance to win!",
			text: "Free Tickets!!!!",
			showModal: false,
			showModalTwo: false,
		};
	},
	methods: {
		toggleModal() {
			this.showModal = !this.showModal;
		},
		toggleModalTwo() {
			this.showModalTwo = !this.showModalTwo;
		},
	},
};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
h1 {
	border-bottom: 2px solid black;
	display: inline-block;
	padding-bottom: 0.5rem;
}

.modal.sale {
	background: crimson;
	color: white;
}

.modal.sale h1 {
	color: white;
}

button {
	margin: 2rem;
}
</style>
