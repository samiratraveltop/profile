<script>
  import TabunganDetail from "$lib/components/TabunganDetail.svelte";
  import TabunganUmroh from "$lib/components/TabunganUmroh.svelte";
  import { fade, fly } from "svelte/transition";
  import { currentMenuActive } from "$lib/stores.svelte";
  currentMenuActive.current = 'tabungan-umroh';
</script>

<svelte:head>
  <title>Tabungan Umroh - Samira Travel</title>
  <meta name="description" content="tabungan umroh samira travel" />
  <meta
    name="keywords"
    content="tabungan umroh, samira, travel, samira travel, umroh"
  />
</svelte:head>

<div in:fade>
  <TabunganUmroh />
  <TabunganDetail />
</div>
