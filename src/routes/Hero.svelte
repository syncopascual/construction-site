<script lang="ts">
    import { base } from '$app/paths';
    import downArrow from '$lib/icons/down_arrow.svg';
    import herobg from '$lib/img/hero-home/hero-bg.png';

    const { heading, subheading, button_content } = $props();

    function handleAnchorClick(event) {
        event.preventDefault();
        const link = event.currentTarget;
        const anchorId = new URL(link.href).hash.replace('#', '');
        const anchor = document.getElementById(anchorId);
        window.scrollTo({
            top: anchor.offsetTop - 50,
            behavior: 'smooth',
        });
    }
</script>

<div class="h-[100%] w-auto">
    <div class="flex h-full w-full">
        <img src={herobg} alt="background" />
    </div>
    <a href="#three_columns" onclick={handleAnchorClick}>
        <div class="heroscroll content bottom-[10px] h-[30px] w-full">
            <img class="content bottom-0 max-h-[100%] w-auto" src={downArrow} alt="down button" />
        </div>
    </a>
</div>

<style>
    .heroscroll {
        opacity: 40%;
        transition: height 0.5s ease;
    }
    .heroscroll:hover {
        height: 40px;
        cursor: pointer;
    }

    .content {
        position: absolute;
        left: 0;
        right: 0;
        margin-inline: auto;
    }
</style>
