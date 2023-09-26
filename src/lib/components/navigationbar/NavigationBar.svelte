<script lang="ts">
    import NavBarButton from "../buttons/NavBarButton.svelte";

</script>

<div class="sticky">
    <!-- <ul style="display:inline;"> 
        <li style="display:inline;">
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
    </ul> -->
    <NavBarButton text="Startseite" site="/?site="></NavBarButton>
    <NavBarButton text="Blog" site="/?site=blog"></NavBarButton>
    <NavBarButton text="Links" site="/?site=links"></NavBarButton>
    <NavBarButton text="Kontakt" site="/?site="></NavBarButton>
</div>



<style>
    div.sticky {
  position: -webkit-sticky;
  position: sticky;
  top: 10%;
  padding: 40px;
  font-size: 25px;
}
</style>
