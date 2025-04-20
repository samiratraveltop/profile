<script>
  import { promo } from "$lib/data";
  import { register } from "swiper/element/bundle";
  register();
</script>

<!-- feature-section -->
<section class="feature-section centred pt_140 pb_45">
  <div class="auto-container">
    <div class="sec-title mb_50">
      <span class="sub-title gradient-color">{promo.section_title}</span>
      <h2>{@html promo.title}</h2>
    </div>
    <div class="row clearfix">
      <swiper-container
        autoplay={{ delay: 5000, speed: 3000 }}
        breakpoints={{
          320: {
            slidesPerView: 1,
            spaceBetween: 30,
          },
          768: {
            slidesPerView: 3,
            spaceBetween: 30,
          },
        }}
        centeredSlides={true}
      >
        {#each promo.images as item}
          <swiper-slide>
            <!-- <div class="col-lg-4 col-md-6 col-sm-12 feature-block"> -->
            <div class="feature-block-one wow fadeInUp animated">
              <div class="inner-box">
                <figure class="image-box">
                  <img src={item.image_path} alt="" />
                </figure>
              </div>
            </div>
            <!-- </div> -->
          </swiper-slide>
        {/each}
      </swiper-container>
    </div>
  </div>
</section>

<!-- feature-section end -->

<style>
  :global(.clearfix > swiper-container) {
    display: flex;
    justify-content: center;
  }
</style>
