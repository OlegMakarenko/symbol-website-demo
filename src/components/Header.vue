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
	<div class="header">
		<Logo class="logo" />
		<div class="navigation">
			<div class="item not-allowed">
				Nav Item 1
			</div>
			<div class="item not-allowed">
				Nav Item 2
			</div>
			<div class="item not-allowed">
				Nav Item 3
			</div>
			<div class="item not-allowed">
				Nav Item 4
			</div>
			<div class="item not-allowed">
				Nav Item 5
			</div>
			<div class="item">
				<ThemedImage name="ThemeSwitch" style="width: 26px; height: 22px;" @click="changeTheme" />
			</div>
		</div>
	</div>
</template>

<script>
import Logo from '@/components/Logo.vue';
import ThemedImage from '@/components/ThemedImage.vue';

export default {
	name: 'Header',

	components: {
		Logo,
		ThemedImage
	},

	methods: {
		changeTheme() {
			const theme = this.$store.getters['ui/theme'];

            this.$store.dispatch('ui/changeTheme', theme === 'darkmode' ? 'lightmode' : 'darkmode');
        }
	}
};
</script>

<style lang="scss" scoped>
.header {
	position: fixed;
	height: 64px;
	left: 0%;
	right: 0.2%;
	top: 0px;

	display: flex;
	flex-direction: row;
	justify-content: space-between;

	background: var(--color-bg-navbar);

	.logo {
		position: absolute;
		height: 24px;
		left: 16px;
		top: calc(50% - 24px/2);
	}

	.navigation {
		width: 100%;
		height: 100%;
		display: flex;
		justify-content: flex-end;
		align-items: center;

		.item {
			position: static;
			width: 95px;
			height: 22px;
			left: 473px;
			top: 0px;

			/* label */

			font-family: Carbon;
			font-style: normal;
			font-weight: 500;
			font-size: 18px;
			line-height: 120%;
			text-transform: uppercase;

			/* Inside Auto Layout */

			flex: none;
			order: 4;
			flex-grow: 0;
			margin: 0px 24px;
			cursor: pointer;
		}

		.not-allowed {
			cursor: not-allowed;
		}
	}
}
</style>