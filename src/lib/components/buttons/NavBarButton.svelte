<script lang="ts">
    export let text: string;
    export let site: string;
</script>

<a href="{site}" class="button" style="text-align: center;">{text}</a>

<style>
    * {
        padding: 0;
        margin: 0;
        text-decoration: none;
        list-style: none;
        box-sizing: border-box;
    }

    a.button {
        font-family: 'Times New Roman', Times, serif;

    }
</style>