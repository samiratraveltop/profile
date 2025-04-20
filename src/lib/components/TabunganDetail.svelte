<script>
  import VideoSection from "./VideoSection.svelte";
  import BrandSection from "./BrandSection.svelte";
  import { tabunganUmrohDetail } from "$lib/data";
  import ButtonJoin from "./ButtonJoin.svelte";
  import { register } from "swiper/element/bundle";
  register();
  const videoID = tabunganUmrohDetail.youtube.video_id;
  const videoTitle = tabunganUmrohDetail.video_title;
</script>

<!-- project-section -->
<section class="project-section pb_140">
  <div
    class="pattern-layer zoom-fade"
    style="background-image: url(assets/images/shape/shape-5.png);"
  ></div>
  <div class="auto-container">
    <div class="sec-title centred mb_50">
      <span class="sub-title gradient-color"
        >{tabunganUmrohDetail.section_title}</span
      >
      <h2>
        {@html tabunganUmrohDetail.title}
      </h2>
    </div>
    <div class="inner-container">
      <div class="row docs clearfix">
        <swiper-container
          autoplay={{ delay: 5000, speed: 3000 }}
          initialSlide={1}
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
          }}
          centeredSlides={true}
        >
          {#each tabunganUmrohDetail.inner_box.images as item}
            <swiper-slide>
              <div class="feature-block-one wow fadeInUp animated">
                <div class="inner-box">
                  <figure class="image-box">
                    <img src={item.image_path} alt="" />
                  </figure>
                </div>
              </div>
            </swiper-slide>
          {/each}
        </swiper-container>
      </div>
      <div class="more-text centred pt_40">
        <ButtonJoin
          buttonText={tabunganUmrohDetail.button_text}
          phoneNumber={tabunganUmrohDetail.phone_number}
          defaultMessage={tabunganUmrohDetail.button_default_message}
        />
      </div>
    </div>
  </div>
</section>
<!-- project-section end -->

<VideoSection {videoID} {videoTitle} />
<BrandSection />

<style>
  .image-box,
  .image-box > img {
    min-height: 30rem;
  }

  .docs {
    display: flex;
    justify-content: center;
  }

  :global(.video-section) {
    margin-bottom: 10rem;
  }
</style>
