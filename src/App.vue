/*
 *
 * Copyright (c) 2019-present for NEM
 *
 * Licensed under the Apache License, Version 2.0 (the "License ");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 *     http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 *
 */

<template>
	<div v-if="isRenderAllowed" id="app">
		<div class="app-content">
			<div class="width-limiter">
				<transition name="view">
					<router-view :key="$route.fullPath"/>
				</transition>
			</div>
		</div>
		<Header />
		<Footer />
	</div>
	<div v-else id="app">
		<h3 class="text-center">Mobile version is not supported yet!</h3>
	</div>
</template>


<script>
import Header from '@/components/Header.vue';
import Footer from '@/components/Footer.vue';

export default {
	components: {
		Header,
		Footer,
	},

	created() {
		this.$store.dispatch('ui/init');
		window.addEventListener("resize", this.resize);
	},

	destroyed() {
		window.removeEventListener("resize", this.resize);
	},

	data() {
		return {
			isRenderAllowed: window.innerWidth > 860
		}
	},

	computed: {
		theme() {
			return this.$store.getters['ui/theme'];
		}
	},

	methods: {
		resize(e) {
			this.isRenderAllowed = window.innerWidth > 860
		}
	},
};
</script>


<style lang="scss">
html, body, #fullheight {
    height: 100%;
    width: 100%;
    margin: 0;
    padding: 0;
}

#app {
    height: 100vh;
    width: 100%;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: space-between;
    flex-direction: column;
}

.app-content {
    width: 100%;
}

.width-limiter {
    display: block;
    width: 100%;
    margin-left: auto;
    margin-right: auto;
}

.text-center {
	text-align: center;
}
</style>
