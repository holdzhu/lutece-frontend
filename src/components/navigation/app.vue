<template>
	<div>
		<ToolBar
			:profile = "profile"
			:is-authenticated = "isAuthenticated"
			:title = "title"
			@input-toggle-drawer = "toggleEvent = !toggleEvent"
		/>
		<Drawer
			:toggle-event = "toggleEvent"
			:title = "title"
		/>
	</div>
</template>


<script>

import { mapGetters } from 'vuex';
import ToolBar from './toolbar';
import Drawer from './drawer';

export default {

	components: {
		ToolBar,
		Drawer,
	},

	data() {
		return {
			toggleEvent: false,
		};
	},

	computed: {
		...mapGetters({
			profile: 'user/profile',
			isAuthenticated: 'user/isAuthenticated',
			isProgressBarVisible: 'navbar/visible',
			title: 'navbar/title',
		}),
	},
};
</script>
