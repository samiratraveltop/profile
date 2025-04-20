<script>
  let { pageYOffset } = $props();
</script>

<!--Scroll to top-->
<!-- svelte-ignore a11y_click_events_have_key_events, a11y_no_static_element_interactions (because of reasons) -->
<div
  class="scroll-to-top {pageYOffset > 150 ? 'scroll-top-active' : ''}"
  onclick={() => window.scrollTo({ top: 0, behavior: "smooth" })}
>
  <svg class="scroll-top-inner" viewBox="-1 -1 102 102">
    <path d="M50,1 a49,49 0 0,1 0,98 a49,49 0 0,1 0,-98" />
  </svg>
</div>
