<script type="text/typescript">
	export let id: string | undefined = undefined;
	export let value: any = undefined;
	export let required: boolean = false;
	export let label: string;

	export let trailingIcon: boolean | undefined = false;

	$: resolvedId = id ?? ('id-' + Math.random().toString().replace('0.', ''));
</script>

<div class="root">
	<input id={resolvedId} on:input bind:value/>

	<label for={resolvedId} class:required={required}>
		{label}
	</label>

	{#if trailingIcon}
		<div class="trailing-icon-container">
			<slot name="trailing-icon"/>
		</div>
	{/if}
</div>