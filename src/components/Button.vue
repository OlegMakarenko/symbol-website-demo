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
	<div class="button">
		{{ caption }}
	</div>
</template>


<script>
export default {
	name: 'Button',

    props: {
        caption: {
            type: String,
            default: ' '
        }
    },

	methods: {
        changeTheme(theme) {
            this.$store.dispatch('ui/changeTheme', theme);
        }
    }
};
</script>


<style lang="scss" scoped>
.button {
    display: inline-block;
	padding: 13px 26px;
    color: var(--color-button-text);
	background: var(--color-button-bg);
    border-radius: 4px;
    text-align: center;
    text-decoration: var(--font-button-bounded-text-decoration);
    font-size: var(--font-button-bounded-font-size);
    font-family: var(--font-button-bounded-font-family);
    font-weight: var(--font-button-bounded-font-weight);
    font-style: var(--font-button-bounded-font-style);
    font-stretch: var(--font-button-bounded-font-stretch);
    letter-spacing: var(--font-button-bounded-letter-spacing);
    line-height: var(--font-button-bounded-line-height);
    text-transform: var(--font-button-bounded-text-case);
    cursor: pointer;

    &:hover {
        background: var(--color-button-bg-hover);
    }
}
</style>