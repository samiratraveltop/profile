<script>
  import AboutSection from "$lib/components/AboutSection.svelte";
  import BannerSection from "$lib/components/BannerSection.svelte";
  import FeaturePackage  from "$lib/components/FeaturePackage.svelte";
  import AgencySection from "$lib/components/AgencySection.svelte";
  import PackagesSection from "$lib/components/PackagesSection.svelte";
  import Pricing from "$lib/components/Pricing.svelte";
  import BenefitSection from "$lib/components/BenefitSection.svelte";
  import SlideText from "$lib/components/SlideText.svelte";
  import Testimonial from "$lib/components/Testimonial.svelte";
  import VideoSection from "$lib/components/VideoSection.svelte";
  import VisionAndMission from "$lib/components/VisionAndMission.svelte";
  import Intro from "$lib/components/Intro.svelte";
  import WhySamira from "$lib/components/WhySamira.svelte";
  import WhySamiraSlider from "$lib/components/WhySamiraSlider.svelte";
  import { fade } from "svelte/transition";
  import { currentMenuActive } from "$lib/stores.svelte";
  import BrandSection from "$lib/components/BrandSection.svelte";

  if (! currentMenuActive.current){      
      currentMenuActive.current = '';
      if(window.location.hash){
          currentMenuActive.current = window.location.hash.slice(1);
      }
  }
  
</script>

<svelte:head>
	<title>Home - Samira Travel</title>
	<meta name="description" content="samira travel" />
	<meta name="keywords" content="samira, travel, samira travel, umroh" />
</svelte:head>

<div transition:fade={{ duration: 500 }}>
  <BannerSection />
  <Intro />
  <VisionAndMission />
  <AboutSection />
  <PackagesSection />
  <FeaturePackage />
  <VideoSection />
  <AgencySection />
  <BenefitSection />
  <SlideText />
  <WhySamira />
  <WhySamiraSlider />
  <Pricing />
  <Testimonial />
  <BrandSection />
</div>