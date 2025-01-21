<script>
    import { onMount } from 'svelte';

    let background;
    let scrollY = 0;

    const handleScroll = () => {
        scrollY = window.scrollY;
        background.style.transform = `translateY(${scrollY * 0.5}px)`;
    };

    onMount(() => {
        window.addEventListener('scroll', handleScroll);
        return () => {
            window.removeEventListener('scroll', handleScroll);
        };
    });
</script>

<style>
    .parallax-background {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-image: url('https://cloud-3zero0e1y-hack-club-bot.vercel.app/0vecteezy_abstract-gradient-pastel-blue-and-purple-background-neon_8617161-1_1_.jpg');
        background-size: cover;
        background-attachment: fixed;
        z-index: -1;
    }
</style> 
<div class="parallax-background" bind:this={background}></div>