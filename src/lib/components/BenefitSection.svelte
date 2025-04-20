<script>
    import { benefit } from "$lib/data";
</script>
<!-- service-section -->
<section class="service-section pt_140 pb_120 bg-color-1">
    <div class="auto-container">
        <div class="sec-title centred light mb_50">
            <span class="sub-title gradient-color">{benefit.section_title}</span>
            <h2>{@html benefit.title}</h2>
        </div>
        <div class="row clearfix">
            {#each benefit.lists as item, i}
                <div class="col-lg-4 col-md-6 col-sm-12 service-block">
                    <div class="service-block-one pr_5 pb_5">
                        <div class="inner-box">
                            <div class="count-text"><span class="gradient-color">{i + 1}</span></div>
                            <h3><a href={undefined}>{item.title}</a></h3>
                            <p>{@html item.description}</p>
                            <!-- <div class="link-box"><a href={undefined} aria-label="benefit" class="gradient-color"><i class="icon-3"></i></a></div> -->
                        </div>
                    </div>
                </div>
            {/each}
        </div>
    </div>
</section>
<!-- service-section end -->
