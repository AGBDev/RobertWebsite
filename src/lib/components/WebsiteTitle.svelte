<script lang="ts">
    export let title: string = "";
    export let size: number = 1;
    export let visible: boolean = false;
    export let font_family: string = "Times New Roman";

    export const toggle = () => {
        visible = !visible;
    }
</script>


{#if visible}

{#if size == 1}
<h1 style="font-family: '{font_family}';">{title}</h1>
{:else if size == 2}
<h2 style="font-family: '{font_family}';">{title}</h2>
{:else if size == 3}
<h3 style="font-family: '{font_family}';">{title}</h3>
{:else if size == 4}
<h4 style="font-family: '{font_family}';">{title}</h4>
{/if}

{/if}