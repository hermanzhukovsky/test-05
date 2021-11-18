<template>
   <div class="about__item item-about">
      <div class="item-about__icon">
         <img :src="require(`@/assets/img/icons/about/${iconName}`)" alt="">
      </div>
      <div class="item-about__text">
			{{ text }}
      </div>
   </div>
</template>

<script>
export default {
	props: ['text', 'iconName'],
	name: 'about-item',
};
</script>


<style lang="scss">
.item-about {
   display: flex;
   position: relative;
   align-items: center;
   &:before {
      content: '';
      display: block;
      border-radius: 50%;
      flex: 0 0 12px;
      align-self: center;
      margin: 0px 38px 0px 0px;
      height: 12px;
      background-color: #323232;
      position: relative;
      z-index: 2;
      @media (max-width: $md3+px) {
         margin: 0px 25px 0px 0px;
      }
   }
   &:after {
      content: '';
      height: 54px;
      width: 12px;
      display: block;
      position: absolute;
      background-color: #fff;
      top: 50%;
      left: 0;
      transform: translate(0, -50%);
   }
   &__icon {
      flex: 0 0 66px;
      img {
         max-width: 100%;
      }
   }

   &__text {
      flex: 1 1 auto;
      line-height: 18px;
      padding: 0px 0px 0px 20px;
   }
}
</style>