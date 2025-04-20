<script>
  import { umrohFeaturesPackage } from "$lib/data";
</script>

<!-- feature-section -->
<section class="feature-section centred pt_140 pb_45">
  <div class="auto-container">
    <div class="sec-title mb_50">
      <span class="sub-title gradient-color"
        >{umrohFeaturesPackage.section_title}</span
      >
      <h2>{@html umrohFeaturesPackage.title}</h2>
      <p class="pt_45">{@html umrohFeaturesPackage.description}</p>
    </div>
    <div class="row clearfix">
      {#each umrohFeaturesPackage.inner_box.lists as item}
        <div class="col-lg-4 col-md-6 col-sm-12 feature-block">
          <div
            class="feature-block-one wow fadeInUp animated"
            data-wow-delay="00ms"
            data-wow-duration="1500ms"
          >
            <div class="inner-box">
              <figure class="image-box">
                <img src={item.image_path} alt={item.name} />
              </figure>
              <div class="lower-content">
                <h3><a href={undefined}>{item.name}</a></h3>
              </div>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>
<!-- feature-section end -->
