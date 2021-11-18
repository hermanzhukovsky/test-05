<template>
   <div :tab-content="id" class="content-technologies__item" :class="{ _active: isActive }">
      <h3 class="content-technologies__title">{{ title }}</h3>
      <div class="content-technologies__text">
         <p v-for="paragraphs in paragraphs">
				{{ paragraphs }}
         </p>
      </div>
   </div>
</template>

<script>
import { defineComponent } from 'vue';


export default defineComponent ({
	name: "technologies-content-item",
	props: ['paragraphs', 'title', 'id', 'isActive']
});

</script>