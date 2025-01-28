<script lang="ts">
    const captionsUrl = "/path/to/captions.vtt";
    let src = $state(
        "http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4",
    );
    let videoEl;

    function onclick() {
        console.log("Hello");
        src =
            src ==
            "http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4"
                ? "http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/ForBiggerBlazes.mp4"
                : "http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4";
        videoEl.load(); // Reload the video
        videoEl.play(); // Play the video after reloading
    }
</script>

<video bind:this={videoEl} autoplay muted controls>
    <source {src} type="video/mp4" />
    <track
        kind="captions"
        src={captionsUrl}
        srclang="en"
        label="English"
        default
    />
    Your browser does not support the video tag.
</video>

<button on:click={onclick}>Change source</button>
