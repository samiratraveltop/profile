<script>
  import "../app.css";
  import MainHeader from "$lib/components/MainHeader.svelte";
  import MainFooter from "$lib/components/MainFooter.svelte";
  import ScrollToTop from "$lib/components/ScrollToTop.svelte";
  import { chat } from "$lib/data";  
  import PreloaderPage from "$lib/components/PreloaderPage.svelte";
  let { children } = $props();
  let showLoader = $state(true);
  let pageYOffset = $state(0);
  let directionClass = $state("rtl");

  $effect(() => {
    if (!showLoader) {
      window.onscroll = () => {
        pageYOffset = window.scrollY;
      };
    }
  });

  setTimeout(() => {
    showLoader = false;
  }, 500);
</script>

<svelte:head>
  <!-- Google Fonts -->
  <link
    href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300..700&display=swap"
    rel="stylesheet"
  />
  <link
    href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,100..1000;1,9..40,100..1000&display=swap"
    rel="stylesheet"
  />
</svelte:head>
<div class="boxed_wrapper {directionClass === 'ltr' ? 'rtl' : 'ltr'}">
  {#if showLoader}
    <PreloaderPage />
  {:else}
    <!-- page-direction -->
    <div class="page_direction">
      <div class="demo-rtl direction_switch">
        <button class="rtl" onclick={() => directionClass = "ltr"}>RTL</button>
      </div>
      <div class="demo-ltr direction_switch">
        <button class="ltr" onclick={() => directionClass = "rtl"}>LTR</button>
      </div>
    </div>

    <!-- page-direction end -->
    <div class="chat-icon">
      
      <a href={`https://wa.me/${chat.phone_number}?text=${chat.button_default_message}`} aria-label="chat" type="button" class="chat-toggler"
        ><i class="far fa-comment"></i></a
      >
    </div>
    <MainHeader {pageYOffset}/>
    {@render children()}
    <MainFooter />
    <ScrollToTop {pageYOffset} />
  {/if}
</div>
<style>
  a.chat-toggler {
    position: relative;
    display: inline-block;
    width: 50px;
    height: 50px;
    line-height: 50px;
    text-align: center;
    font-size: 26px;
    color: #fff;
    background: var(--theme-color);
    border-radius: 50%;
  }
</style>