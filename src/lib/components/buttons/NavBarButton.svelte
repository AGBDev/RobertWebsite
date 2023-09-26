<script lang="ts">
    export let text: string;
    export let site: string;
</script>



<div style="display:inline;">
    <a class="button" href={site} style="font-size: xx-large; color:red; font-family:'Times New Roman', Times, serif">
        <div style="display:inline;">{text}</div>
    </a>
</div>