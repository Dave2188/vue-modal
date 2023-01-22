<template>
	<div class="backdrop" @click.self="closeModal">
		<div class="modal" :class="{ sale: theme === 'sale' }">
			<slot>Default Content</slot>
			<div class="sign" id="sign">
				<slot name="userData"></slot>
			</div>
			<div class="actions">
				<slot name="links"></slot>
			</div>
		</div>
	</div>
</template>

<script>
import { slotFlagsText } from "@vue/shared";

export default {
	props: ["theme"],
	methods: {
		closeModal() {
			this.$emit("close");
		},
	},
	components: { slotFlagsText },
};
</script>

<style>
.modal {
	width: 400px;
	padding: 20px;
	margin: 100px auto;
	background: white;
	border-radius: 10px;
}
.modal .actions {
	text-align: center;
	margin: 3rem 0 1rem 0;
}

.modal .actions a {
	color: #333;
	padding: 0.8rem;
	border: 1px solid #eee;
	border-radius: 0.4rem;
	text-decoration: none;
	margin: 1rem;
}

#sign {
	text-align: right;
}

#sign fieldset {
	border-radius: 0.5rem;
}

#sign input {
	width: 10rem;
	margin: 0 3rem;
}

.backdrop {
	top: 0;
	position: fixed;
	background: rgba(0, 0, 0, 0.5);
	width: 100%;
	height: 100%;
}
.modal h1 {
	color: turquoise;
}
</style>
