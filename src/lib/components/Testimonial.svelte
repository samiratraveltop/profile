<script>
  import { testimonials } from "$lib/data";
  import { register } from "swiper/element/bundle";
  register();
</script>

<!-- testimonial-section -->
<section class="testimonial-section pt_150 pb_150">
  <div class="pattern-layer">
    <div
      class="pattern-1"
      style="background-image: url(assets/images/shape/shape-4.png);"
    ></div>
    <div
      class="pattern-2 zoom-fade"
      style="background-image: url(assets/images/shape/shape-5.png);"
    ></div>
  </div>
  <div class="auto-container">
    <div class="row align-items-center">
      <div class="col-lg-6 col-md-12 col-sm-12 image-column">
        <swiper-container
          autoplay={{ delay: 5000 }}
          centeredSlides={true}
          spaceBetween={30}
          pagination={true}
        >
          {#each testimonials.awards as item}
            <swiper-slide>
              <div class="image-box mr_40">
                <figure class="image awards">
                  <img src={item.image_path} alt="awards" />
                </figure>
                <!-- <div class="icon-box"><div class="icon gradient-color"><i class="icon-7"></i></div></div> -->
              </div>
            </swiper-slide>
          {/each}
        </swiper-container>
      </div>
      <div class="col-lg-6 col-md-12 col-sm-12 content-column">
        <div class="content-box ml_40">
          <div class="sec-title mb_50">
            <span class="sub-title gradient-color"
              >{testimonials.section_title}</span
            >
            <h2>{@html testimonials.title}</h2>
          </div>
          <div
            class="single-item-carousel owl-carousel owl-theme owl-dots-none nav-style-one"
          >
            <swiper-container
              autoplay={{ delay: 3000 }}
              slidesPerView={1}
              spaceBetween={30}
              centeredSlides={true}
            >
              {#each testimonials.comments as item}
                <swiper-slide>
                  <div class="testimonial-content">
                    <ul class="rating">
                      <li><i class="icon-32"></i></li>
                      <li><i class="icon-32"></i></li>
                      <li><i class="icon-32"></i></li>
                      <li><i class="icon-32"></i></li>
                      <li><i class="icon-32"></i></li>
                    </ul>
                    <p>{@html item.comment}</p>
                    <div class="author-box">
                      <figure class="thumb-box">
                        <img src={item.image_path} alt="" />
                      </figure>
                      <div class="inner">
                        <h3>{item.name}</h3>
                        <span class="destination">{item.address}</span>
                      </div>
                    </div>
                  </div>
                </swiper-slide>
              {/each}
            </swiper-container>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- testimonial-section end -->
<style>
  figure.awards {
    max-width: fit-content;
  }

  .owl-carousel {
    display: block;
  }

  swiper-container,
  swiper-slide {
    display: flex;
    justify-content: center;
    align-self: center;
    height: 100%;
  }
</style>
