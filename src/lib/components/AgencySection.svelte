<script>
  import { agency } from "$lib/data";
</script>

<!-- feature-section -->
<section class="feature-section centred pt_140 pb_45">
  <div class="auto-container">
    <div class="sec-title mb_50">
      <span class="sub-title gradient-color">{agency.section_title}</span>
      <h2>{@html agency.title}</h2>
    </div>
    <div class="row clearfix">
      {#each agency.inner_box.lists as item}
        <div class="col-lg-3 col-md-6 col-sm-12 feature-block">
          <div
            class="feature-block-one wow fadeInUp animated"
            data-wow-delay="00ms"
            data-wow-duration="1500ms"
          >
            <div class="inner-box">
              <!-- <figure class="image-box"><img src="assets/images/resource/feature-1.jpg" alt=""></figure> -->
              <div class="lower-content">
                <h3><a href={undefined}>{item.title}</a></h3>
                <!-- <p>Potensi Pasar Di Indonesia Sangat Besar, karena:</p> -->
                <ul>
                  {#each item.lists as it}
                    <li>{it}</li>
                  {/each}
                </ul>
              </div>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- feature-section end -->

<style>
  ul {
    padding-left: 1rem;
  }
  
  ul,
  li {
    list-style: square;
  }

  :global(.lower-content li) {
    text-align: left;
  }
</style>
