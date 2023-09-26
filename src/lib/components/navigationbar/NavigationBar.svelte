<script lang="ts">
    import NavBarButton from "../buttons/NavBarButton.svelte";

</script>

<div class="sticky">
    <ul>
        <li style="display:inline">
            <NavBarButton text="Startseite" site="/?site="></NavBarButton>
        </li>
        |
        <li style="display:inline">
            <NavBarButton text="Blog" site="/?site=blog"></NavBarButton>
        </li>
        |
        <li style="display:inline">
            <NavBarButton text="Links" site="/?site=links"></NavBarButton>
        </li>
        |
        <li style="display:inline">
            <NavBarButton text="Kontakt" site="/?site="></NavBarButton>
        </li>
    </ul>
</div>



<style>
    a {
        color:blue;
    }

    div.sticky {
  position: -webkit-sticky;
  position: sticky;
  top: 0;
  /* background-color: #666; */
  padding: 40px;
  font-size: 25px;
}
</style>
