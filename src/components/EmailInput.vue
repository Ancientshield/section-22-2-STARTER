<template>
	<input
		type="email"
		class="form-control"
		placeholder="E-mail"
		:value="modelValue"
		@input="update($event)"
		:class="{
			'is-valid': email.length >= 4 && email.length > 0,
			'is-invalid': email.length && email.length > 0,
		}"
	/>
</template>

<script>
	export default {
		name: 'EmailInput',
		props: ['email'],
		methods: {
			update() {
				this.$emit('update:email', $event.target.value);
			},
		},
	};
</script>
