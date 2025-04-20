<script>
  import { reasonsSlider } from "$lib/data";
  import { register } from "swiper/element/bundle";
  register();
</script>

<section class="service-style-two alternat-2 pt_0 pb_140">
  <div
    class="pattern-layer"
    style="background-image: url(assets/images/shape/shape-4.png);"
  ></div>
  <div class="auto-container">
    <div class="sec-title mb_50 centred">
      <!-- <span class="sub-title gradient-color">Layanan</span> -->
      <h2>{@html reasonsSlider.title}</h2>
    </div>
    <div
      class="five-item-carousel owl-carousel owl-theme owl-nav-none dots-style-one"
    >
      <swiper-container
        autoplay={{ delay: 1000 }}
        speed={4000}
        initialSlide={1}
        effect="slide"
        fadeEffect={{ crossFade: false }}
        centeredSlides={true}
        pagination={{
          hideOnClick: true,
        }}
        breakpoints={{
          320: {
            slidesPerView: 1,
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
        }}
      >
        {#each reasonsSlider.inner_box.lists as item}
          <swiper-slide>
            <div class="service-block-two pr_5 pb_5 block-shadow">
              <div class="inner-box">
                <h3><a href={undefined}>{item.title}</a></h3>
              </div>
            </div>
          </swiper-slide>
        {/each}
      </swiper-container>
    </div>
  </div>
</section>

<style>
  .service-style-two.alternat-2 .inner-box,
  .five-item-carousel .inner-box {
    padding: 20px !important;
  }
  .inner-box h3 {
    text-align: center;
  }

  .owl-carousel {
    display: block;
  }
</style>
