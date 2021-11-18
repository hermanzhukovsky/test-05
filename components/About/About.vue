<template>
   <section id="about" class="page__about about">
      <div class="about__container _container">
         <div class="about__block">
            <h2 class="about__title _title">About us</h2>
            <div class="about__image _ibg">
               <img src="@/assets/img/about_image.jpg" alt="">
            </div>
         </div>
         <div class="about__content">
            <div class="about__items">
					<about-item v-for="item in items" v-bind="item"></about-item>
            </div>
         </div>
      </div>
   </section>
</template>

<script>
import AboutItem from '@/components/About/AboutItem';

import { defineComponent } from 'vue';
export default defineComponent({
   data() {
      return {
         items: [
            {
               text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt',
               iconName: '01.png',
            },
            {
               text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt',
               iconName: '02.png',
            },
            {
               text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt',
               iconName: '03.png',
            },
            {
               text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt',
               iconName: '04.png',
            },
         ],
      };
   },
   name: 'v-about',
	components: {
		AboutItem
	}
});
</script>

<style lang="scss">
.about {
   &__container {
      @media (min-width: 1080px) {
         display: flex;
         align-items: center;
      }
   }
   &__block {
      position: relative;
      @media (min-width: 1080px) {
         flex: 0 0 800 / $maxWidthContainer * 100%;
      }
      @media (max-width: 1080px) {
         margin: 0px -15px 30px -15px;
      }
   }

   &__title {
      text-align: left;
      position: absolute;
      z-index: 0;
      left: 110px;
      top: 26px;
      z-index: 2;
      @media (max-width: $md1+px) {
         left: 15px;
      }
   }

   &__image {
      width: 100%;
      padding: 0px 0px 71.1% 0px;
      @media (max-width: 1080px) {
         padding: 0px 0px 40% 0px;
      }
      @media (max-width: $md3+px) {
         padding: 0px 0px 70% 0px;
      }
   }
   &__content {
      @media (min-width: 1080px) {
         flex: 1 1 auto;
         padding: 0px 0px 0px 71 / $maxWidthContainer * 100%;
      }
   }
   &__items {
      position: relative;
      &:before {
         content: '';
         width: 5px;
         height: calc(100% - 6px);
         position: absolute;
         top: 6px;
         left: 3px;
         background: url('~@/assets/img/dotts.png') 0 0 repeat;
      }
   }

   &__item {
      &:not(:last-child) {
         margin: 0px 0px 70px 0px;
      }
      &:first-child,
      &:last-child {
         position: relative;
         z-index: 2;
         background-color: #fff;
      }
   }
}

</style>
