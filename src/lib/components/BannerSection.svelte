<script>
  import { fly } from "svelte/transition";
  import { banners } from "$lib/data";
  import ButtonJoin from "./ButtonJoin.svelte";
  import { register } from 'swiper/element/bundle';
  register();
</script>

<!-- banner-section -->
<section class="banner-section p_relative">
  <div
    class="pattern-layer"
    style="background-image: url(assets/images/shape/shape-1.png);"
  ></div>
  <div
    class="banner-carousel owl-theme owl-carousel owl-dots-none nav-style-one"
  >
    <swiper-container
      autoplay={{ delay: 3000, speed: 3000 }}
      initialSlide={1}                
      slidesPerView={1}
      effect="fade"
      fadeEffect={{ crossFade: false }}
      centeredSlides={true}
    >
    {#each banners as item , i }
      <swiper-slide>
        <div class="slide-item p_relative">
          <div
            class="bg-layer swiper-zoom-target"
            style={`background-image: url(${item.image_path});`}
          ></div>
          <div class="auto-container">
            <div class="content-box">
              <span
                class="upper-text {i == 0 || i % 2 == 0 ? 'gradient-color' : 'gradient-colorx'}"
                in:fly={{ y: -50, duration: 2000 }}
                >{item.label_text}</span
              >
              <h2 in:fly={{ x: 50, duration: 2000 }} class:gradient-colorx={i % 2 != 0 }>
                {item.title_text}
              </h2>
              <p in:fly={{ y: 50, duration: 2000 }} class:gradient-colorx={i % 2 != 0 }>
                <strong
                  >{item.description_text}</strong
                >
              </p>
              <div in:fly={{ x: -50, duration: 2000 }}>
                <ButtonJoin phoneNumber={item.phone_number} buttonText={item.button_text} defaultMessage={encodeURI(item.button_default_message)} />
              </div>
            </div>
          </div>
        </div>
      </swiper-slide>       
    {/each}
    </swiper-container>
  </div>
</section>

<!-- banner-section end -->

<style>
  .gradient-colorx {
    color: aliceblue;
    font-weight: bold;
  }
  .owl-carousel {
    display: block;
  }
  .banner-carousel .content-box .upper-text {
    transform: translateY(3rem);
  }
  
  .banner-carousel .content-box h2,
  .banner-carousel .content-box p,
  .banner-carousel .content-box span,
  .banner-carousel .content-box div {
    opacity: 1 !important;
  }
  .bg-layer {
    background-size: contain;
    min-height: 50rem;
  }
  :global(.swiper-slide-active > .slide-item > .bg-layer) {
    transform: scale(1.5);
  }
  :global(.banner-carousel .content-box .btn-box){
    opacity: 1 !important;
  }
</style>
