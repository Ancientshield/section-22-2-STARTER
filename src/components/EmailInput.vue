<template>
	<input
		type="email"
		class="form-control"
		placeholder="E-mail"
		:value="modelValue"
		@input="update($event)"
		:class="{
			'is-valid': validateEmail(email),
			'is-invalid': !validateEmail(email),
		}"
	/>
</template>

<script>
	import validateEmail from '../validate-email.js';

	export default {
		name: 'EmailInput',
		props: ['email'],
		methods: {
			update() {
				this.$emit('update:email', $event.target.value);
			},
			validateEmail,
		},
	};
</script>
