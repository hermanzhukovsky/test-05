<template>
   <a @click.prevent="changeTab" href="" :tab="id" class="technologies__item item-technologies" :class="{ _active: isActive }">
      <div class="item-technologies__body">
         <div class="item-technologies__brand">
            <img :src="require(`@/assets/img/technologies/${brandLogo}`)" alt="">
         </div>
         <div class="item-technologies__name">{{ brandName }}</div>
      </div>
   </a>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent ({
	name: "technologies-item",
	props: ['brandLogo', 'brandName', 'id', 'isActive'],
	methods: {
		changeTab() {
			this.$emit('tabtoggle', this.id);
		}
	}
});
</script>

<style lang="scss">
.item-technologies {
	text-align: center;

	&._active {
		.item-technologies__brand {
			transform: scale(1.2);
			&::before {
				background-color: transparent;
			}
		}
		.item-technologies__name {
			opacity: 1;
			visibility: visible;
		}
	}
	@media (any-hover: hover) {
		&:hover {
			.item-technologies__brand {
				transform: scale(1.2);
				&::before {
					background-color: transparent;
				}
			}
			.item-technologies__name {
				opacity: 1;
				visibility: visible;
			}
		}
	}
	&__brand {
		height: 105px;
		transition: all 0.3s ease 0s;
		position: relative;
		&::before {
			content: '';
			position: absolute;
			top: 0;
			left: 0;
			width: 100%;
			height: 100%;
			background-color: rgba(255,255,255,0.66);
			transition: all 0.3s ease 0s;
			z-index: 2;
		}
		@media (min-width: $md2+px) {

		}
		img {
			max-width: 100%;
			max-height: 100%;
		}
	}
	
	&__name {
		font-size: 24px;
		color: #323232;
		transition: all 0.3s ease 0s;
		opacity: 0;
		visibility: hidden;
		margin: 29px 0px 0px 0px;
		@media (max-width: $md2+px) {
			display: none;
		}
	}
}

</style>