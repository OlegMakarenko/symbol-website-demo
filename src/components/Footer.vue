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
		<div @click="changeTheme('lightmode')">Lightmode</div>
        <div @click="changeTheme('darkmode')">Darkmode</div>
	</div>
</template>
<script>


export default {
	name: 'Footer',

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
}
</style>