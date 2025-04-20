<script>
  import { tabunganUmroh } from "$lib/data";
</script>

<section class="about-style-four centred pt_140 pb_140">
  <div class="auto-container">
    <div class="content-box">
      <div class="sec-title mb_50">
        <span class="sub-title gradient-color"
          >{tabunganUmroh.section_title}</span
        >
        <h2>{@html tabunganUmroh.title}</h2>
      </div>
      <p>
        {@html tabunganUmroh.description}
      </p>
      <!-- <a href="index-4.html" class="theme-btn btn-one"><span class="text">Learn More</span><i class="icon-3"></i></a> -->
      <div class="inner-box block-shadow">
        <h3>{@html tabunganUmroh.inner_box.title}</h3>
        <div class="list-inner">
          <ul class="list-style-one">
            {#each tabunganUmroh.inner_box.lists as item}
              <li>{item}</li>
            {/each}
          </ul>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .content-box .inner-box {
    padding: 2rem;
    border-radius: 31px;
  }
  .content-box .inner-box .list-inner:before {
    display: none;
  }
  .content-box .inner-box .list-inner {
    display: flex;
  }
  .inner-box h3 {
    text-align: start;
    margin-bottom: 2rem;
  }

  ul.list-style-one {
    width: 100%;
    gap: 1rem;
  }

  ul.list-style-one li {
    display: flex;
    text-align: left;
  }
  .about-style-four .content-box {
    margin-bottom: 2rem;
  }
</style>
