<script>
  import { slidesText } from "$lib/data";
  import { register } from "swiper/element/bundle";
  register();
</script>

<div class="slide-text-outer p_relative pb_80 pt_60">
  <div class="text-box">
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
      {#each { length: slidesText.length < 5 ? 10 : 1 }, i}
        {#each slidesText as item (item)}
          <swiper-slide>
            <div class="item">{item}</div>
          </swiper-slide>
        {/each}
      {/each}
    </swiper-container>
  </div>
</div>

<style>
  :root {
    --swiper-wrapper-transition-timing-function: linear;
  }

  .slide-text-outer {
    position: relative;
    background: #f2f2f2;
    padding: 40px 0px;
  }

  .slide-text-outer .text-box {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
  }
  swiper-container {
    width: 100%;
  }
  .slide-text-outer .text-box .item {
    position: relative;
    display: inline-block;
    font-size: 30px;
    line-height: 40px;
    font-family: var(--title-font);
    font-weight: 700;
    text-transform: uppercase;
    color: var(--title-color);
    margin: 0rem;
  }

  .slide-text-outer .text-box .item::before {
    position: absolute;
    content: "\e904";
    font-family: "icomoon";
    font-size: 40px;
    top: 0px;
    right: -80px;
  }
</style>
