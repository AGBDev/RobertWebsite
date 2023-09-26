<script lang="ts">
    export let text: string;
    export let site: string;
</script>

<a href="{site}" class="button" style="text-align: center;">{text}</a>

<style>
    a.button {
    -webkit-appearance: button;
    -moz-appearance: button;
    appearance: button;

    text-decoration: none;
    color: initial;
}
</style>