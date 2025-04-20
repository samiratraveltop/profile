<script>
  import { brands } from "$lib/data";
  import { register } from 'swiper/element/bundle';
  register();
</script>

<!-- brand-section -->
<section class="brand-section pb_100">
  <div class="auto-container">
    <div
      class="five-item-carousel owl-carousel owl-theme owl-nav-none owl-dots-none"
    >
    <swiper-container
    autoplay={{ delay: 1 }}
    speed={4000}
    breakpoints={{
      320: {
        slidesPerView: 2,
        spaceBetween: 30,
      },
      480: {
        slidesPerView: 3,
        spaceBetween: 30,
      },
      768: {
        slidesPerView: 3,
        spaceBetween: 30,
      },
      1024: {
        slidesPerView: 5,
        spaceBetween: 30,
      },
      1200: {
        slidesPerView: 10,
        spaceBetween: 30,
      },
    }}
    allowTouchMove={false}
    loop={true}
  >  
  {#each { length: (brands.images.length < 5 ? 10 : 1) }, i}
      {#each brands.images as item}
      <swiper-slide>
        <figure class="brand-logo">
          <a href={undefined}><img src={item.image_path} alt={item.name} /></a>
        </figure>
        </swiper-slide>
      {/each}
    {/each}
      </swiper-container>
    </div>
  </div>
</section>

<!-- brand-section end -->

<style>
  .owl-carousel {
    display: block;
    /* justify-content: center; */
  }

  .auto-container {
    max-width: 100%;
  }

  :root {
    --swiper-wrapper-transition-timing-function: linear;
  }

</style>
