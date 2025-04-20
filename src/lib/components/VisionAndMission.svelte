<script>
  import { vision } from "$lib/data";
</script>

<!-- chooseus-section -->
<section class="chooseus-section pl_70 pr_70">
  <div class="outer-container pt_140 pb_150 bg-color-1">
    <div class="auto-container">
      <div class="sec-title mb_50 light">
        <span class="sub-title gradient-color">{vision.section_title}</span>
        <h2>{@html vision.title}</h2>
      </div>
      <div class="row clearfix cont">
        <div class="col-lg-6 col-md-12 col-sm-12 title-column">
          <figure class="image-box mr_20">
            <img src={vision.image_path} alt="vision" />
          </figure>
        </div>
        <div class="col-lg-6 col-md-12 col-sm-12 content-column">
          <div class="content-box ml_20">
            <div class="chooseus-block-one">
              <div class="inner-box">
                <h3><a href={undefined}>{@html vision.content}</a></h3>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- chooseus-section end -->

<style>
  .content-box {
    height: 100%;
    display: flex;
    justify-content: center;
    justify-items: center;
    align-items: center;
  }
  .chooseus-block-one,
  .chooseus-block-one .inner-box {
    height: 100%;
    display: flex;
    justify-content: center;
    justify-items: center;
    align-items: center;
  }
  .chooseus-block-one .inner-box a {
    color: #fff;
    text-decoration: none;
    align-items: center;
  }
  .chooseus-block-one .inner-box h3 {
    align-items: center;
    margin-top: 2rem;
    text-align: left;
  }
  .outer-container {
    border-radius: 3rem;
  }
  .image-box {
    width: 100%;
  }
  .title-column img {
    border-radius: 1rem;
  }
  @media only screen and (max-width: 1200px) {
    .chooseus-section {
      padding: 0px;
      border-radius: 0px;
    }
    .outer-container {
      border-radius: 0rem;
    }
  }
</style>
