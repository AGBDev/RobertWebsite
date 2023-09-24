<script lang="ts">
    export let title: string = "";
    export let size: number = 1;
    export let visible: boolean = false;
</script>


{#if visible}

{#if size == 1}
<h1>{title}</h1>
{:else if size == 2}
<h2>{title}</h2>
{:else if size == 3}
<h3>{title}</h3>
{:else if size == 4}
<h4>{title}</h4>
{/if}

{/if}