<script>
  import { pricing } from "$lib/data";
  import ButtonJoin from "./ButtonJoin.svelte";
</script>

<!-- pricing-section -->
<section class="pricing-section pt_140 pb_120">
  <div class="auto-container">
    <div class="sec-title centred mb_30">
      <span class="sub-title gradient-color">{pricing.section_title}</span>
      <h2>{@html pricing.title}</h2>
    </div>
    <div class="tabs-box">
      <!-- <div class="tab-btn-box">
                        <ul class="tab-btns tab-buttons">
                            <li class="tab-btn active-btn" data-tab="#tab-1">Monthly</li>
                            <li class="tab-btn" data-tab="#tab-2">Yearly</li>
                        </ul>
                    </div> -->
      <div class="tabs-content">
        <div class="tab active-tab">
          <div class="row clearfix price-list">
            {#each pricing.inner_box.lists as item}
              <div class="col-xl-4 col-lg-6 col-md-8 col-sm-12 pricing-block">
                <div class="pricing-block-one pr_5 pb_5 block-shadow">
                  <div class="pricing-table">
                    <div class="table-header">
                      <span class="sub-title gradient-color">{item.name}</span>
                      <h2>{item.price}</h2>
                      <span class="text">{item.description}</span>
                      <p>{item.subname}</p>
                    </div>
                    <div class="table-content">
                      <ul class="feature-list">
                        {#each item.lists as list}
                          <li><i class="icon-4"></i><span>{list}</span></li>
                        {/each}
                      </ul>
                      <ButtonJoin
                        phoneNumber={item.phone_number}
                        buttonText={item.button_text}
                        defaultMessage={item.button_default_message}
                      />
                    </div>
                  </div>
                </div>
              </div>
            {/each}
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- pricing-section end -->

<style>
  section {
    background-color: black;
  }
  section .sec-title > h2 {
    color: aliceblue;
  }
  .price-list {
    display: flex;
    justify-content: center;
  }
</style>
