<section class="max-width">
	<slot />
</section>

<style module="true">
	.max-width {
		max-width: var(--max-width);
		width: -webkit-fill-available;
		margin: 0 auto;
		background-color: 'pink';
		
	}

	@media all and (max-width: 900px) {
		.max-width {
			padding-left: var(--padding);
			padding-right: var(--padding);
			max-width: var(--max-width-sm);
		}
	}

	@media all and (max-width: 1080px) {
		.max-width {
			max-width: var(--max-width-md);
		}
	}
</style>
