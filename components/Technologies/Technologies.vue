<template>
   <section id="technologies" class="page__technologies technologies">
      <div class="technologies__container _container">
         <div class="technologies__block">
            <h2 class="technologies__title _title">Our technologies</h2>
            <div class="technologies__items">
					<technologies-item @tabtoggle="toggleTab" v-for="item in items" v-bind="item"></technologies-item>
            </div>
         </div>
         <div class="technologies__content content-technologies">
				<technologies-content-item v-for="item in content" v-bind="item"></technologies-content-item>
			</div>
		</div>
   </section>
</template>

<script>
import { defineComponent } from 'vue';
import TechnologiesItem from './TechnologiesItem.vue';
import TechnologiesContentItem from './TechnologiesContentItem.vue';

export default defineComponent({
	name: "v-technologies",
	data() {
		return {
			items: [
				{ brandName: "Twilio", brandLogo: "01.png", id: 1, isActive: false, },
				{ brandName: "Android", brandLogo: "02.png", id: 2, isActive: false },
				{ brandName: "Raspberry", brandLogo: "03.png", id: 3, isActive: false },
				{ brandName: "Vue", brandLogo: "04.png", id: 4, isActive: false },
				{ brandName: "Mongoose", brandLogo: "05.png", id: 5, isActive: false },
				{ brandName: "Python", brandLogo: "06.png", id: 6, isActive: false },
				{ brandName: "Django", brandLogo: "07.png", id: 7, isActive: false },
				{ brandName: "MariaDB", brandLogo: "08.png", id: 8, isActive: false },
				{ brandName: "MongoDB", brandLogo: "09.png", id: 9, isActive: false },
			],
			content: [
				{
					id: 1,
					isActive: false,
					title: "Twilio", 
					paragraphs: ["Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error.", "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error.", "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error."]
				},
				{
					id: 2,
					isActive: false,
					title: "Android", 
					paragraphs: ["Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error.", "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error."]
				},
				{
					id: 3,
					isActive: false,
					title: "Raspberry", 
					paragraphs: ["Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error."]
				},
				{
					id: 4,
					isActive: false,
					title: "Vue", 
					paragraphs: ["Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error.", "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error."]
				},
				{
					id: 5,
					isActive: false,
					title: "Mongoose", 
					paragraphs: ["Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error.", "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error.", "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error."]
				},
				{
					id: 6,
					isActive: false,
					title: "Python", 
					paragraphs: ["Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error.", "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error."]
				},
				{
					id: 7,
					isActive: false,
					title: "Django", 
					paragraphs: ["Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error.", "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error."]
				},
				{
					id: 8,
					isActive: false,
					title: "MariaDB", 
					paragraphs: ["Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error.", "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error.", "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error."]
				},
				{
					id: 9,
					isActive: false,
					title: "MongoDB", 
					paragraphs: ["Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto deleniti labore et laboriosam consectetur, perferendis suscipit odit quo error saepe provident dolorem iure earum culpa assumenda nemo doloribus. Incidunt, error."]
				},
			],
			activeBrand: {},
			activeContentItem: {},
		}
	},
	methods: {
		toggleTab(id) {
			const item = this.items.find(item => item.id == id);
			const contentItem = this.content.find(item => item.id == id);
			this.activeBrand.isActive = false;
			this.activeContentItem.isActive = false;

			item.isActive = true;
			contentItem.isActive = true;

			this.activeBrand = item;
			this.activeContentItem = contentItem;
		}
	},
	mounted() {
		this.activeBrand = this.items[0];
		this.activeContentItem = this.content[0];

		this.activeBrand.isActive = true;
		this.activeContentItem.isActive = true;
	},
	components: {
		TechnologiesItem,
		TechnologiesContentItem,
	}
})

</script>

<style lang="scss">
.technologies {
	position: relative;
	&:after {

		@media (min-width: $md2+px) {
			content: '';
			position: absolute;
			width: 424px;
			top: 10px;
			right: 0;
			height: 652px;
			opacity: 0.12;
			background: url('~@/assets/img/technologies_background.png') 0 0 / cover no-repeat;
		}
	}
	&__container {
		position: relative;
		
		@media (min-width: $md2+px) {
			display: flex;
			align-items: flex-start;
		}
		&:before {
			@media (min-width: $md2+px) {
				content: "";
				position: absolute;
				top: 0;
				right: 0;
				background-color: $greenColor;
				width: 450px;
				height: 100%;
				@include adaptiv-value("border-top-left-radius", 50, 20, 1);
				@include adaptiv-value("border-bottom-left-radius", 50, 20, 1);
				@media (min-width: $md1+px) {
					width: 100%;
					left: 69%;
				}
			}

		}

	}
	
	&__block {
		@media (min-width: $md2+px) {
			flex: 1 1 auto;
			padding: 0px 105 / $maxWidthContainer * 100% 0px 0px;
		}
	}

	&__title {
		@include adaptiv-value("margin-bottom", 60, 40, 1);
	}

	&__items {
		display: flex;
		align-items: center;
		flex-wrap: wrap;
		
		@include adaptiv-value("margin-right", -50, -10, 1);
		@include adaptiv-value("margin-left", -50, -10, 1);
	}
	
	&__item {
		padding: 0px 50px;
		@include adaptiv-value("margin-bottom", 60, 30, 1);
		@include adaptiv-value("padding-right", 50, 10, 1);
		@include adaptiv-value("padding-left", 50, 10, 1);
		flex: 0 1 25%;
		@media (max-width: 1120px) {
			flex: 0 1 33.333%;
		}
		@media (max-width: $md2+px) {
			flex: 0 1 16.666%;
		}
		@media (max-width: $md3+px) {
			flex: 0 1 20%;
		}
		@media (max-width: 600px) {
			flex: 0 1 25%;
		}
		@media (max-width: 450px) {
			flex: 0 1 33.333%;
		}

	}
	
	&__content {
		@media (min-width: $md2+px) {
			flex: 0 0 430px;
		}
		@media (max-width: $md2+px) {
			margin: 0px -15px;
		}
	}

}


.content-technologies {
	position: relative;
	padding: 70px 0px 15px 70px;
	z-index: 2;
	@media (max-width: $md2+px) {
		background-color: $greenColor;
		padding: 40px 15px;
	
	}
	&__item {
		display: none;
		&._active {
			display: block;
		}
	}
	&__title {
		font-family: "Lato";
		text-align: center;
		color: #fff;
		@include adaptiv-value("font-size", 36, 28, 1);
		&:not(:last-child) {
			margin: 0px 0px 30px 0px;
		}
	}

	&__text {
		@include adaptiv-value("font-size", 16, 14, 1);
		line-height: 24 / 16 * 100%;
		color: #fff;
		p:not(:last-child) {
			@include adaptiv-value("margin-bottom", 30, 20, 1);
		}
	}
}

</style>

