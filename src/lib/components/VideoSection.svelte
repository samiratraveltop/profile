<script>
  import Modal from "./Modal.svelte";
  import { homeVideo } from "$lib/data";
  let showModal = $state(false);
  let {
    videoID = null,
    videoTitle = null,
    videoWidth = 560,
    videoHeight = 315,
    videoImagePath = null,
  } = $props();
</script>

<!-- video-section -->
<section class="video-section centred">
  <div
    class="bg-layer parallax-bg"
    style={videoImagePath
      ? `background-image: url(${videoImagePath});`
      : `background-image: url(${homeVideo.image_path});`}
  ></div>
  <div class="auto-container">
    <div class="content-box">
      <h2>{@html videoTitle ? videoTitle : homeVideo.title}</h2>
      <div class="video-btn">
        <!-- <a aria-label="popup-video" href="https://www.youtube.com/watch?v=DQv8xfmrNu4&amp;t=28s" class="lightbox-image" data-caption=""><i class="icon-6"></i><span class="border-animation"></span><span class="border-animation border-1"></span><span class="border-animation border-2"></span><span class="border-animation border-3"></span></a> -->
        <a
          aria-label="popup-video"
          href={undefined}
          class="lightbox-image"
          data-caption=""
          onclick={() => (showModal = true)}
          ><i class="icon-6"></i><span class="border-animation"></span><span
            class="border-animation border-1"
          ></span><span class="border-animation border-2"></span><span
            class="border-animation border-3"
          ></span></a
        >
      </div>
    </div>
  </div>
</section>

<!-- video-section end -->
<Modal bind:showModal>
  {#snippet header()}
    <div></div>
  {/snippet}
  {#snippet child()}
    <iframe
      width={videoWidth ? videoWidth : homeVideo.youtube.video_width}
      height={videoHeight ? videoHeight : homeVideo.youtube.video_height}
      src={videoID
        ? `https://www.youtube.com/embed/${videoID}`
        : `https://www.youtube.com/embed/${homeVideo.youtube.video_id}`}
      title={videoTitle ? videoTitle : homeVideo.youtube.video_title}
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      referrerpolicy="strict-origin-when-cross-origin"
      allowfullscreen
    ></iframe>
  {/snippet}
</Modal>
