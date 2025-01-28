<script lang="ts">
    import type { PageData } from "./$types";

    let { data }: { data: PageData } = $props();
    const captionsUrl = "/path/to/captions.vtt"; // Replace with your actual captions file
</script>

<video controls>
    <source
        src="http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4"
        type="video/mp4"
    />
    <track
        kind="captions"
        src={captionsUrl}
        srclang="en"
        label="English"
        default
    />
    Your browser does not support the video tag.
</video>
