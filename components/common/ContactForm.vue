<template>
	<form class="intro__form contact-form" @submit.prevent="validateForm" action="#">
		<div class="contact-form__body" :class="{ 'contact-form__body_bottom':  isBottom }">
			<div class="contact-form__row">
				<div class="contact-form__column">
					<div class="contact-form__label">Name</div>
					<div class="contact-form__input">
						<input v-model="name" autocomplete="off" type="text" placeholder="Your name" class="input">
					</div>
				</div>
				<div class="contact-form__column">
					<div class="contact-form__label">Phone number</div>
					<div class="contact-form__input">
						<input ref="phoneNumberInput" :class="{ _error: showError }" v-model="phoneNumber" autocomplete="off" type="tel" placeholder="+433 33333333" class="input">
					</div>
					<div class="contact-form__error" :class="{ _active: showError }">The phone number is not valid</div>
				</div>
			</div>
			<button class="contact-form__btn btn">contact us</button>
		</div>
	</form>
</template>

<script>
	import { defineComponent } from 'vue';
	import { InputMask } from "@/helpers.js";
	export default defineComponent({
		name: "contact-form",
		props: {
			isBottom: Boolean,
		},
		data() {
			return {
				phoneNumber: "",
				name: "",
				layout: "+___ ________",
				showError: false 
			}
		},
		mounted() {
			new InputMask({
				selector: this.$refs.phoneNumberInput,
				layout: this.layout,
			});
		},
		methods: {
			validateForm() {
				if (this.layout.length == this.phoneNumber.length - 1) {
					alert('The data has been sent to the server');
					this.phoneNumber = "";
					this.name = "";
					if (this.showError) this.showError = false;
				} else {
					this.showError = true;
					this.$refs.phoneNumberInput.focus();
				}
			}
		}
	});
</script>

<style lang="scss">
.contact-form {
	&__body {
		background-color: #fff;
		&_bottom {
			@media (min-width: 860px) {
				@include adaptiv-value("padding", 35, 15, 1);
				border: 1px solid #cfddd5;
				border-radius: 3px;
			}
			.contact-form__btn {
				position: relative;
				left: 50%;
				transform: translate(-50%, 0);
			}
		}
	}
	&__row {
		@media (min-width: 640px) {
			display: flex;
			margin-left: -18px;
			margin-right: -18px;
		}
		&:not(:last-child) {
			margin-bottom: 31px;
		}
	}
	&__column {
		@media (min-width: 640px) {
			flex: 0 1 50%;
			padding: 0px 18px;
		}
		@media (max-width: 640px) {
			&:not(:last-child) {
				margin: 0px 0px 30px 0px;
			}
		}
	}
	
	&__label {
		font-weight: 700;
		margin: 0px 0px 8px 0px;
	}
	&__error {
		color: #f00;
		font-size: 12px;
		font-weight: 700;
		margin: 5px 0px 0px 0px;
		display: none;
		&._active {
			display: block;
		}
	}
	&__btn {
		&_center {
			position: relative;
			left: 50%;
			transform: translate(-50%, 0);
		}
	}
}
</style>

