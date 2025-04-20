<script>
  import Promotion from "$lib/components/Promotion.svelte";
  import { currentMenuActive } from "$lib/stores.svelte";
  currentMenuActive.current = 'promo';

</script>
<svelte:head>
  <title>Promo - Samira Travel</title>
  <meta name="description" content="tabungan umroh samira travel" />
  <meta
    name="keywords"
    content="promo travel, promo umroh, samira, travel, samira travel, umroh"
  />
</svelte:head>

<Promotion />