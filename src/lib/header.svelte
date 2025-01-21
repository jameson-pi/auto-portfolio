<script>
    import info from "$lib/info.json";
    import parrot from "$lib/headbangingparrot.gif"
</script>
<style>
    header {
        background-color: #f8f9fa;
        padding: 20px;
        border-bottom: 1px solid #ddd;
        display: flex;
        justify-content: space-between;
    }
</style>
<header>
        <div><h2>{info.name}'s Portfolio</h2></div>
        <div><img src={parrot} alt="headbanging parrot" style="width:50px;height:50px;"/></div>
</header>