<template>
	<div class="pkpHeader -pkpClearfix">
		<span class="pkpHeader__title">
			<slot />
		</span>
		<div v-if="hasActions" class="pkpHeader__actions">
			<slot name="actions" />
		</div>
	</div>
</template>

<script>
export default {
	computed: {
		hasActions() {
			return this.$slots.actions;
		}
	}
};
</script>

<style lang="less">
@import '../../styles/_import';

.pkpHeader {
	padding: 1rem 2rem;
}

.pkpHeader__title {
	display: inline-block;
	margin: 0;
	padding: 0.25rem 0;
	font-size: @font-base;
	font-weight: @bold;
	line-height: 1.5em;

	.pkpSpinner {
		margin-left: 0.5rem;
	}
}

.pkpHeader__actions {
	float: right;
	margin-left: 1rem;
	margin-top: -1px; // button borders

	> * {
		display: inline-block;
	}

	> * + * {
		margin-left: 0.25rem;
	}
}
</style>
