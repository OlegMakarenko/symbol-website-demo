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
	<div class="footer">
		<Logo />
		<div class="navigation">
			<div class="section">
				<h3>Mobile app</h3>
				<div class="label">Features</div>
				<div class="label">Live share</div>
				<div class="label">Video record</div>
			</div>
			<div class="section">
				<h3>Community</h3>
				<div class="label">Featured artists</div>
				<div class="label">The Portal</div>
				<div class="label">Live events</div>
			</div>
			<div class="section">
				<h3>Company</h3>
				<div class="label">About us</div>
				<div class="label">Contact us</div>
				<div class="label">History</div>
			</div>
		</div>
		<div class="mode-swith" @click="changeTheme('lightmode')">Swith to Lightmode</div>
        <div class="mode-swith" @click="changeTheme('darkmode')">Swith to Darkmode</div>
	</div>
</template>


<script>
import Logo from '@/components/Logo.vue';

export default {
	name: 'Footer',

	components: {
		Logo
	},

	methods: {
        changeTheme(theme) {
            this.$store.dispatch('ui/changeTheme', theme);
        }
    }
};
</script>

<style lang="scss" scoped>
.footer {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: flex-start;
	padding: 32px 16px 32px 48px;
	background: var(--color-bg-footer);
	color: var(--color-text-footer);

	.navigation {
		margin-top: 48px;
		margin-bottom: 18px;
		display: flex;
		flex-direction: row;


		.section {
			display: block;
			width: 173px;
			margin-right: 30px;
		}

		.label {
			cursor: not-allowed;
		}

		.label:first-child {
			margin-top: 15px;
		}
	}

	.mode-swith {
		color: var(--color-button-text-unbounded);
		text-decoration: var(--font-button-unbounded-text-decoration);
		font-size: var(--font-button-unbounded-font-size);
		font-family: var(--font-button-unbounded-font-family);
		cursor: pointer;
	}
}
</style>