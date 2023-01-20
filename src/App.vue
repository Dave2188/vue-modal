<template>
	<h1>{{ title }}</h1>
	<p>Welcome!!!</p>
	<div v-if="showModal">
		<Modal theme="sale" @close="toggleModal">
			<h1>{{ this.header }}</h1>
			<p>{{ this.text }}</p>
		</Modal>
	</div>
	<button @click="toggleModal">Open Modal</button>
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
		};
	},
	methods: {
		toggleModal() {
			this.showModal = !this.showModal;
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
</style>
