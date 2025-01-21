<script>
    import info from "$lib/info.json";
    import Fluid from "svelte-fluid-header"
</script>
<header>
    <Fluid>
        <div slot="left"><h2>{info.name}'s Portfolio</h2></div>
    </Fluid>
</header>