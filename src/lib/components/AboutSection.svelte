<script>
  import { about } from "$lib/data";
  import ButtonJoin from "./ButtonJoin.svelte";
</script>

<!-- about-section -->
<section class="about-section pt_70 pb_140" id="about">
  <div
    class="pattern-layer"
    style="background-image: url(assets/images/shape/shape-4.png);"
  ></div>
  <div class="auto-container">
    <div class="row clearfix">
      <div class="col-lg-6 col-md-12 col-sm-12 content-column">
        <div class="content_block_one">
          <div class="content-box mr_100">
            <div class="sec-title mb_45">
              <span class="sub-title gradient-color">{about.section_title}</span
              >
              <h2>{@html about.title}</h2>
            </div>
            <div class="text-box">
              <p>{@html about.description}</p>
            </div>
            <div class="inner-box block-shadow mb_45">
              <!-- <h3>Slogan</h3> -->
              <div class="list-inner">
                <ul class="list-style-one">
                  {#each about.inner_box.lists as item}
                    <li>{item}</li>
                  {/each}
                </ul>
              </div>
            </div>
            <ButtonJoin
              phoneNumber={about.phone_number}
              buttonText={about.button_text}
              defaultMessage={about.button_default_message}
            />
          </div>
        </div>
      </div>
      <div class="col-lg-6 col-md-12 col-sm-12 image-column">
        <div class="image_block_one">
          <div class="image-box pl_170">
            <div class="image-shape">
              <div
                class="shape-1 zoom-fade"
                style="background-image: url(assets/images/shape/shape-2.png);"
              ></div>
              <div
                class="shape-2"
                style="background-image: url(assets/images/shape/shape-3.png);"
              ></div>
            </div>
            <figure class="image image-1">
              <img src={about.image_path_2} alt="" width="200" />
            </figure>
            <figure class="image image-2">
              <img src={about.image_path_1} alt="" width="200" />
            </figure>
            <div class="experience-box block-shadow">
              <h3>{@html about.image_description}</h3>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- about-section end -->

<style>
  .content_block_one .content-box .inner-box {
    padding: 2rem;
  }
  .content_block_one .content-box .inner-box .list-inner:before {
    display: none;
  }

  ul.list-style-one {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    justify-content: center;
    justify-items: center;
  }

  ul.list-style-one li {
    font-size: 35px;
  }

  .image_block_one .image-box .image-2 img {
    width: 300px;
    height: 300px;
  }

  .image_block_one .image-box .image-1 img {
    width: 420px;
    height: 470px;
  }

  .image_block_one .image-box .experience-box h3 {
    font-size: 18px;
  }

  .about-section {
    padding-top: 10rem;
  }

  @media only screen and (max-width: 480px) {
    .image_block_one .image-box .image-2 img {
      width: 100%;
      height: auto;
    }
  }
</style>
