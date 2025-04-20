<script>
  import Icon from "@iconify/svelte";
  import { reasons } from "$lib/data";
</script>

<!-- service-style-two -->
<section class="service-style-two pt_140 pb_120">
  <div
    class="pattern-layer"
    style="background-image: url(assets/images/shape/shape-4.png);"
  ></div>
  <div class="auto-container">
    <div class="sec-title mb_50 centred">
      <span class="sub-title gradient-color">{reasons.section_title}</span>
      <h2>{@html reasons.title}</h2>
    </div>
    <div class="row clearfix">
      {#each reasons.inner_box.lists as item}
        <div class="col-lg-4 col-md-6 col-sm-12 service-block">
          <div class="service-block-two pr_5 pb_5 block-shadow">
            <div class="inner-box">
              <div class="icon-box">
                <!-- <i class="icon-16"></i> -->
                <Icon icon={item.icon} width="48" height="48" />
              </div>
              <h3><a href={undefined}>{item.title}</a></h3>
              <p>{@html item.description}</p>
              <!-- <div class="link"><a href={undefined} aria-label="why us"><i class="icon-3"></i></a></div> -->
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>
<!-- service-style-two end -->
