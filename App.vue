<template>
	<div class="wrapper">
		<v-header />
		<main class="page">
			<v-intro />
			<v-about />
			<v-technologies />
			<v-contacts />
		</main>
		<v-footer />
	</div>
</template>

<script>
import vHeader from '@/components/Header/Header';
import vIntro from '@/components/Intro/Intro';
import vAbout from '@/components/About/About';
import vTechnologies from '@/components/Technologies/Technologies';
import vContacts from '@/components/Contacts/Contacts';
import vFooter from '@/components/Footer/Footer';

import { defineComponent } from 'vue';
import { ibg } from '@/helpers.js';

export default defineComponent ({
	name: 'app',
	components: {
		vHeader,
		vIntro,
		vAbout,
		vTechnologies,
		vContacts,
		vFooter,
	},
	mounted() {
		ibg();
	}
});
</script>

