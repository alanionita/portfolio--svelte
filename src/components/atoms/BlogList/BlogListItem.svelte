<script lang="ts">
	import Link from '../Link.svelte';
    export let slug: string = '';
	export let text: string = '';
	export let created: string = '';
	import {parse, format} from 'date-fns';
	let datetime = parse(created, 'dd/MM/yyyy', new Date());
	let datestr = format(datetime, 'EEEE, dd MMMM yyyy')
	import { base } from '$app/paths';
</script>

<li>
    <Link to="{base}/blog/{slug}" text={text} />
    <aside>
        <time datetime={datetime.toISOString()}>Created on - {datestr}</time>
    </aside>
</li>

<style module="true">
	li {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		color: white;
		font-size: var(--fluid-type-h2);
		padding-bottom: 2rem;
	}
	li:last-child {
		padding-bottom: 0rem;
	}   
	time {
		color: var(--color-primary);
		font-weight: 700;
	}
</style>
