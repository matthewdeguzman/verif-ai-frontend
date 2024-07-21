<script lang='ts'>
    import { videoLink } from '../../stores.js'; // Adjust the path as needed
    import { onMount } from 'svelte';

    let url = '';

    onMount(() => {
        videoLink.subscribe(value => {
        url = getYouTubeEmbedUrl(value);
        });
    });

    function getYouTubeEmbedUrl(url: string) {
        const videoId = getYouTubeID(url);
        if (videoId) {
            return `https://www.youtube.com/embed/${videoId}`;
        }
        return '';
    }

    function getYouTubeID(url: string) {
        const regExp = /(?:youtube\.com\/(?:[^\/\n\s]+\/\S+\/|(?:v|e(?:mbed)?)\/|.*[?&]v=)|youtu\.be\/)([a-zA-Z0-9_-]{11})/;
        const match = url.match(regExp);
        return match ? match[1] : null;
    }

</script>

<iframe  class="w-full h-[350px] rounded-box border-2 border-[#D9D9D9] shadow-md" src={url} title="YouTube video player" frameborder="0" allow="clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" ></iframe>
