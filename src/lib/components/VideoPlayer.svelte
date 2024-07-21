<script>
    import { videoLink } from '../../stores.js'; // Adjust the path as needed
    import { onMount } from 'svelte';

    let url = '';

    onMount(() => {
        videoLink.subscribe(value => {
        url = value;
        });
    });
</script>

<iframe  class="w-full h-[350px] rounded-box border-2 border-[#D9D9D9] shadow-md" src={url} title="YouTube video player" frameborder="0" allow="clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" ></iframe>
