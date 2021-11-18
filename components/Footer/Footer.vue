<template>
	<footer class="footer">
		<div class="footer__container _container">
			<div class="footer__body">
				<div class="footer__top">
					<div class="footer__main main-footer">
						<div class="main-footer__top">
							<a href="#home" @click="scrollToSection" class="main-footer__arrow fas fa-arrow-up"></a>
							<a href="" class="main-footer__logo">
								<img src="@/assets/img/logo_white.png" alt="">
							</a>
							<div class="main-footer__menu menu">
								<ul class="menu__list">
									<li class="menu__item"><a href="#home" class="menu__link menu__link_white menu__link_home fas fa-home"><span>home</span></a></li>
									<li class="menu__item"><a href="#about" class="menu__link menu__link_white"><span>about us</span></a></li>
									<li class="menu__item"><a href="#technologies" class="menu__link menu__link_white"><span>our technologies</span></a></li>
									<li class="menu__item"><a href="#contacts" class="menu__link menu__link_white"><span>contacts</span></a></li>
								</ul>
							</div>
						</div>
						<div class="main-footer__social social">
							<a href="" class="social__item">
								<img src="@/assets/img/icons/social/facebook_small.png" alt="">
							</a>
							<a href="" class="social__item">
								<img src="@/assets/img/icons/social/youtube_small.png" alt="">
							</a>
							<a href="" class="social__item">
								<img src="@/assets/img/icons/social/instagram_small.png" alt="">
							</a>
						</div>
					</div>
					<div class="main-footer__contacts contacts-footer">
						<a href="" class="contacts-footer__item fas fa-map-marker">Praha 8, Troja, Pomořanská 475/8</a>
						<a href="tel:+4222222222" class="contacts-footer__item fas fa-phone">+422 2222222</a>
						<a href="mailto:josef.novotny@ltd.com" class="contacts-footer__item fas fa-envelope">josef.novotny@ltd.com</a>
					</div>
				</div>
				<div class="footer__copy">All rights reserved</div>
			</div>
		</div>
	</footer>
</template>

<script>
import { scrollToSection } from '@/helpers.js';
import { defineComponent } from 'vue';

export default defineComponent({
	name: "v-footer",
	methods: {
		scrollToSection(e) {
			scrollToSection(e);
		}
	}
})
</script>

<style lang="scss">
.footer {
	padding: 31px 0px 15px 0px;
	background-color: $greenColor;
	&__top {
		@media (min-width: 1045px) {
			display: flex;
		}
		
	}
	&__main {
		
		
		@media (min-width: 1045px) {
			padding: 0px 57 / $maxWidthContainer * 100% 0px 0px;
			flex: 1 1 auto;
		}
		@media (max-width: 1045px) {
			&:not(:last-child) {
				margin: 0px 0px 30px 0px;
			}
			
		}
	}

	&__contacts {
		@media (min-width: 1045px) {
			flex: 0 0 280px;
		}
	}

	&__copy {
		margin: 15px 0px 0px 0px;
		font-family: "Lato";
		color: #535353;
		font-weight: 700;
	}
}

.main-footer {

	&__top {
		display: flex;
		flex-wrap: wrap;
	}

	&__arrow {
		font-size: 36px;
		color: #fff;
		align-self: flex-end;
		margin: 0px 38px 0px 0px;
		@media (min-width: $md1+px) {
			margin: 0px 68px 0px 0px;
		}

	}

	&__logo {
		flex: 0 0 148px;
		img {
			max-width: 100%;
		}
	}
	&__menu {
		flex: 1 1 100%;
		@media (min-width: $md3+px) {
			flex: 1 1 auto;
			align-self: center;
			padding: 0px 0px 0px 66 / $maxWidthContainer * 100%;
			justify-content: flex-end;
		}
		@media (max-width: $md3+px) {
			margin: 25px 0px 0px 0px;
		}
	}

	&__social {
		margin: 25px 0px 0px 0px;
		@media (min-width: 1045px) {
			justify-content: flex-end;
		}
	}
}

.social {
	display: flex;
	align-items: center;
	&__item {
		&:not(:last-child) {
			margin: 0px 21px 0px 0px;
		}
	}
}

.contacts-footer {
	&__item {
		display: flex;
		align-items: center;
		color: #fff;
		font-weight: 500;
		&:not(:last-child) {
			margin: 0px 0px 18px 0px;
		}
		&:before {
			flex: 0 0 35px;
			min-height: 35px;
			border-radius: 50%;
			background-color: #fff;
			color: $greenColor;
			display: inline-flex;
			justify-content: center;
			align-items: center;
			font-size: 16px;
			margin: 0px 9px 0px 0px;
		}
	}
}
</style>

