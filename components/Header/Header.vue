<template>
	<header ref="header" class="header">
		<div class="header__wrapper">
			<div class="header__container _container">
				<div class="header__body">
					<a href="" class="header__logo">
						<img src="@/assets/img/logo.png" alt="">
					</a>
					<div class="header__menu menu">
						<nav class="menu__body" :class="{ _active: menuIsOpen }">
							<ul class="menu__list">
								<li class="menu__item"><a @click="scrollToSection" href="#home" class="menu__link menu__link_home fas fa-home"><span>home</span></a></li>
								<li class="menu__item"><a @click="scrollToSection" href="#about" class="menu__link"><span>about us</span></a></li>
								<li class="menu__item"><a @click="scrollToSection" href='#technologies' class="menu__link"><span>our technologies</span></a></li>
								<li class="menu__item"><a @click="scrollToSection" href='#contacts' class="menu__link"><span>contacts</span></a></li>
							</ul>
						</nav>
					</div>
					<a href="tel:+4222222222" class="header__phone fas fa-phone"><span>+422 2222222</span></a>
					<button type="button" class="icon-menu" @click="toggleMenu" :class="{ _active: menuIsOpen }">
						<span></span>
						<span></span>
						<span></span>
					</button>
				</div>
			</div>
		</div>
	</header>
</template>

<script>
	import { defineComponent } from 'vue';
	import { scrollToSection } from '@/helpers.js';
	export default defineComponent({
		name: 'v-header',
		data() {
			return {
				headerObserver: null,
				menuIsOpen: false,
				unlock: true,
			}
		},
		mounted() {
			this.headerObserver = new IntersectionObserver(this.onElementObserve);
			this.headerObserver.observe(this.$refs.header);
		},
		methods: {
			onElementObserve(entries) {
				if (entries[0].isIntersecting) {
					if (this.$refs.header) {
						this.$refs.header.classList.remove('_scroll');
					}
				} else {
					if (this.$refs.header) {
						this.$refs.header.classList.add('_scroll');
					}
				}
			},
			toggleMenu() {
				if (this.unlock) {
					document.body.classList.toggle("_lock");
					this.menuIsOpen = !this.menuIsOpen;
					this.unlock = false;
					setTimeout(() => {
						this.unlock = true;
					}, 300);
				}
			},
			scrollToSection(e) {
				scrollToSection(e);
				if (window.matchMedia("(max-width: 767.98px)").matches) {
					this.toggleMenu();
				}
			}
		}
	});

</script>


<style lang="scss">
	.header {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	min-height: 76px;
	&._scroll {
		.header__wrapper {
			background-color: #fff;
			border-bottom: 1px solid rgba(38, 159, 88, 0.5);
			
		}
		.header__body {
			min-height: 76px;
		}
		.header__phone {
			color: #000;
			&::before {
				color: #fff;
				background-color: $greenColor;
			}
		}
		.menu__body {
			&::before {
				height: 76px;
			}
		}
	}
	&__wrapper {
		transition: all 0.3s ease 0s;
		position: relative;
		position: fixed;
		top: 0;
		left: 0;
		z-index: 10;
		width: 100%;
	}
	&__body {
		transition: min-height 0.3s ease 0s;
		min-height: 130px;
		align-items: center;
		display: flex;
		@media (max-width: $md1+px) {
			min-height: 120px;
		}
		@media (max-width: $md2+px) {
			min-height: 90px;
		}
	}

	&__logo {
		flex: 0 0 137px;
		position: relative;
		z-index: 5;
		img {
			max-width: 100%;
		}
	}

	&__menu {
		flex: 1 1 auto;
		padding: 0px 25px 0px 103 / $maxWidthContainer * 100%;
	}

	&__phone {
		transition: all 0.3s ease 0s;
		color: #fff;
		display: inline-flex;
		align-items: center;
		flex-direction: row-reverse;
		position: relative;
		z-index: 11;
		@media (max-width: 1060px) {
			color: #000;
		}
		span {
			@media (max-width: $md2+px) {
				display: none;
			}
			@media (min-width: $md2+px) {
				margin: 0px 16px 0px 0px;
				flex: 1 0 auto;
			}
		}
		@media (max-width: $md3+px) {
			&:not(:last-child) {
				margin: 0px 20px 0px 0px;
			}
			
		}
		&::before {
			min-height: 31px;
			flex: 0 0 31px;
			background-color: #fff;
			color: $greenColor;
			border-radius: 50%;
			display: inline-flex;
			justify-content: center;
			align-items: center;
			@media (max-width: 1060px) {
				color: #fff;
				background-color: $greenColor;
			}
		}
	}
}
//=================================================================================================================================

.menu {

	&__icon {
	}

	&__body {
		@media (max-width: $md3+px) {
			position: fixed;
			top: 0;
			left: -100%;
			width: 100%;
			height: 100%;
			transition: all ease 0.3s 0s;
			background-color: #fff;
			overflow: auto;
			z-index: 2;
			padding: 110px 15px 15px 15px; 
			&._active {
				left: 0;
				&:before {
					content: "";
					position: fixed;
					top: 0;
					left: 0;
					width: 100%;
					height: 90px;
					background-color: #fff;
					border-bottom: 1px solid rgba(38, 159, 88, 0.5);
					z-index: 2;
				}
			}
		}
	}

	&__list {
		@media (min-width: $md3+px) {
			display: flex;
			align-items: center;
			position: relative;
			z-index: 2;
		}
	}

	&__item {
		&:not(:last-child) {
			margin: 0px 59px 0px 0px;
		}
		@media (max-width: $md1+px) {
			&:not(:last-child) {
				margin: 0px 40px 0px 0px;
			}
			
		}
		@media (max-width: $md3+px) {
			&:not(:last-child) {
				margin: 0px 0px 26px 0px;
			}
		}
	}

	&__link {
		span {
			color: #000;
			@media (min-width: $md3+px) {
				transition: all 0.3s ease 0s;
				position: relative;
				&:before {
					content: '';
					transition: all 0.3s ease 0s;
					position: absolute;
					bottom: -20px;
					opacity: 0;
					visibility: hidden;
					left: 50%;
					transform: translate(0, -50%);
					width: 6px;
					height: 6px;
					border-radius: 50%;
					background-color: $greenColor;
				}
			}
		}

		@media (any-hover: hover) {
			&:hover {
				span {
					color: $greenColor;
					&::before {
						opacity: 1;
						visibility: visible;
						bottom: -14px;
					}
				}
			}
		}
		&_home {
			&::before {
				color: $greenColor;
				margin: 0px 11px 0px 0px;
				@media (max-width: $md3+px) {
					display: none;
				}
			}
		}
		&_white {
			span {
				color: #000;
				&:before {
					@media (min-width: $md3+px) {
						background-color: #fff;
					}
					
				}
				@media (max-width: $md3+px) {
					color: #fff;
				}
				@media (any-hover: hover) {
					&:hover {
						color: #fff;
					}
				}
			}
		}
		&_white.menu__link_home {
			&::before {
				@media (min-width: $md3+px) {
					color: #fff;
				}
			}
		}
		@media (max-width: $md3+px) {
			font-size: 20px;
		}
	}
}


.icon-menu {
	@media (max-width: $md3+px) {
		display: block;
		position: relative;
		width: 30px;
		height: 18px;
		cursor: pointer;
		z-index: 3;
		span {
			transition: all 0.3s ease 0s;
			position: absolute;
			left: 0px;
			top: calc(50% - 1px);
			width: 100%;
			height: 2px;
			background-color: $greenColor;
		}
		span:first-child {
			top: 0px;
		}
		span:last-child {
			top: auto;
			bottom: 0px;
		}
		&._active {
			span {
				transform: scale(0);
				&:first-child {
					transform: rotate(-45deg);
					top: calc(50% - 1px);
				}
				&:last-child {
					transform: rotate(45deg);
					bottom: calc(50% - 1px);
				}
			}
		}
	}
}
</style>