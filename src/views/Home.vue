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
	<div class="home">
		<div class="section">
			<img src="../assets/Delivery.png" class="image image1" />
			<div class="hero fit-screen">
				<h2 class="title">
					Greetings Space Pirates! We are making the world a better place 
					through the power of technical innovation.
				</h2>
				<div class="body">
					We do this with X, Y, and Z. Lorem ipsum dolor sit amet, 
					consectetur adipiscing elit. Sit ornare pulvinar sed elit sit.
				</div>
				<Button caption="CTA" />
			</div>
		</div>

		<div class="section dark">
			<div class="hero">
				<h1 class="title">
					Benefits
				</h1>
				<div class="body">
					Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
					Sit ornare pulvinar sed elit sit.
				</div>
			</div>
			<div class="benefits-container">
				<div class="benefit-item">
					<ThemedImage name="Restrictions" class="benefit-image" />
					<h3 class="title">
						Title
					</h3>
					<div class="benefit-description">
						Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
						sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
					</div>
					<Link caption="LEARN MORE" />
				</div>	
				<div class="benefit-item">
					<ThemedImage name="Mosaics" class="benefit-image" />
					<h3 class="title">
						Title
					</h3>
					<div class="benefit-description">
						Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
						sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
					</div>
					<Link caption="LEARN MORE" />
				</div>	
				<div class="benefit-item">
					<ThemedImage name="Plugins" class="benefit-image" />
					<h3 class="title">
						Title
					</h3>
					<div class="benefit-description">
						Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
						sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
					</div>
					<Link caption="LEARN MORE" />
				</div>	
			</div>
			
		</div>

		<div class="section">
			<img src="../assets/Passport.png" class="image image2" />
			<div class="hero fit-screen">
				<h1 class="title">
					Get a wallet
				</h1>
				<div class="body">
					A wallet lets you plug into Symbol and manage your funds. 
					XYM is the currency of Symbol, ready for use in dApps. Get both here.
				</div>
				<Button caption="Get Wallet" />
			</div>
		</div>

		<div class="section dark">
			<img src="../assets/Treasure-Chest.png" class="image image3" />
			<div class="hero fit-screen">
				<h1 class="title">
					Contribute
				</h1>
				<div class="body">
					Symbol is community built, community focused, and community powered. 
					Let’s build together. See how you can get involved.
				</div>
				<Button caption="to the dev portal, arggh!" />
			</div>
		</div>

		<div class="section">
			<img src="../assets/Factory.png" class="image image4" />
			<div class="hero over-screen">
				<h1 class="title">
					LEARN
				</h1>
				<div class="body" style="font-size: 25px; line-height: 30px;">
					Knowledge is power. Read, learn, and see what you can do with Symbol.
				</div>
				<Link caption="LEARN" class="button" />
			</div>
		</div>
	</div>
</template>
<script>
import Button from '@/components/Button.vue';
import Link from '@/components/Link.vue';
import ThemedImage from '@/components/ThemedImage.vue';

export default {
	name: 'Home',

	components: {
		Button,
		Link,
		ThemedImage
	},

	mounted() {

	}
};
</script>

<style lang="scss" scoped>
.home {
	background: var(--color-bg-gray);
	min-height: 100%;
	padding: 72px 0px;
	
	.section {
		position: relative;
		padding-top: 19px;

		.image {
			position: absolute;
			bottom: 0;
			right: 0;
		}

		.image1 {
			height: 80%;
		}

		.image2 {
			width: 50%;
			max-width: 800px;
		}

		.image3 {
			height: 100%;
		}

		.image4 {
			width: 92%;
			left: 50%;
			transform: translateX(-50%);
			bottom: 0;
			overflow: hidden;
		}

		.hero {
			position: relative;
			width: 70%;
			max-width: 1000px;
			padding-left: 46px;

			.body {
				width: 70%;
			}

			.button {
				margin-top: 22px;
			}
		}

		.fit-screen {
			min-height: 90vh;
		}

		.over-screen {
			min-height: 120vh;
		}
	}
	
	.dark {
		background: var(--color-bg-dark);
	}

	.benefits-container {
		display: flex;
		justify-content: space-around;
		flex-direction: row;
		padding-top: 44px;
		padding-bottom: 25px;

		.benefit-item {
			display: flex;
			justify-content: space-between;
			align-items: center;
			flex-direction: column;
		}

		.benefit-image {
			height: 144px;
		}

		.benefit-description {
			width: 280px;
			font-family: Protipo;
			font-style: normal;
			font-weight: normal;
			font-size: 18px;
			line-height: 150%;

			text-align: center;
			margin: 8px 0px;
		}
	}
}
</style>