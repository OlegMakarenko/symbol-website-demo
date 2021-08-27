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
	<img :src="src" />
</template>

<script>
import MosaicsDarkmodeSrc from '../assets/darkmode/Mosaics.png';
import MosaicsLightmodeSrc from '../assets/lightmode/Mosaics.png';
import PluginsDarkmodeSrc from '../assets/darkmode/Plug-Ins.png';
import PluginsLightmodeSrc from '../assets/lightmode/Plug-Ins.png';
import RestrictionsDarkmodeSrc from '../assets/darkmode/Restrictions.png';
import RestrictionsLightmodeSrc from '../assets/lightmode/Restrictions.png';

const images = {
    Mosaics: [MosaicsDarkmodeSrc, MosaicsLightmodeSrc],
    Plugins: [PluginsDarkmodeSrc, PluginsLightmodeSrc],
    Restrictions: [RestrictionsDarkmodeSrc, RestrictionsLightmodeSrc],
};

export default {
	name: 'Image',

    props: {
        name: {
            type: String,
            required: true,
            validator: item => Object.keys(images).includes(item)
        }
    },

	computed: {
        imageIndex() {
            return this.$store.getters['ui/theme'] === 'lightmode' ? 1 : 0;
        },

        src() {
            return image[this.name][this.imageIndex];
        }
    }
};
</script>