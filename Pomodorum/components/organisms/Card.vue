<template>
	<div
		class="bg-white
		rounded-md
		flex flex-1
		w-full mt-8
		lg:mt0
		shadow-sm
		dark-mode"
		:style="{transition: 'background 0.7s ease, color 0.7s ease'}"
	>
		<Challenge v-if="currentChallenge" v-bind="currentChallenge"	/>
		<StartCycle v-else />
		<LevelUpModal />
	</div>
</template>

<script lang="ts">
import Vue from 'vue';
import { mapGetters } from 'vuex';

import LevelUpModal from '~/components/atoms/LevelUpModal.vue';
import StartCycle from '~/components/atoms/StartCycle.vue';
import Challenge from '~/components/molecules/Challenge.vue';

export default Vue.extend({
	components: {
		Challenge,
		StartCycle,
		LevelUpModal,
	},
	computed: mapGetters('Challenges', ['currentChallenge']),
});
</script>
