<script>
  import { intro } from "$lib/data";
</script>

<section class="about-style-four centred pt_140 pb_140">
  <div class="auto-container">
    <div class="content-box">
      <div class="sec-title mb_50">
        <span class="sub-title gradient-color">{intro.section_title}</span>
        <h2>{intro.title}</h2>
      </div>
      <p>{@html intro.quote}</p>
      <div class="inner-box block-shadow">
        <h3>{intro.inner_box.title}</h3>
        <div class="list-inner">
          <ul class="list-style-one">
            {#each intro.inner_box.lists.left as item}
              <li>{item}</li>
            {/each}
          </ul>
          <ul class="list-style-one">
            {#each intro.inner_box.lists.right as item}
              <li>{item}</li>
            {/each}
          </ul>
        </div>
      </div>

      <div class="mt_45 problem-container">
        <h4>{intro.problem.title}</h4>
        <div class="problem">
          <div class="list-inner">
            <ul class="list-style-one">
              {#each intro.problem.lists as item}
                <li>{item}</li>
              {/each}
            </ul>
          </div>
        </div>
        <p>{@html intro.problem.description}</p>
      </div>
    </div>
    <!-- <div class="image-box">
            <div class="image-shape zoom-fade" style="background-image: url(assets/images/shape/shape-5.png);"></div>
            <figure class="image image-hov-one"><img src="assets/images/resource/about-3.png" alt=""></figure>
        </div> -->
  </div>
  <div class="auto-container">
    <div class="sec-title mb_50 centred">
      <!-- <span class="sub-title gradient-color">Layanan</span> -->
      <h2>{@html intro.subcontent.title}</h2>
    </div>
    <div class="row way">
      {#each intro.subcontent.lists as item}
        <div class="service-block-two pr_5 block-shadow">
          <div class="inner-box">
            <h3><a href={undefined}>{item}</a></h3>
          </div>
        </div>
      {/each}
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

  .problem {
    margin-top: 1rem;
  }

  .problem li::before {
    content: "\f057";
    font-family: "Font Awesome 5 Pro";
  }

  .problem-container p {
    text-align: left;
    margin-top: 2rem;
  }

  .way {
    display: flex;
    justify-content: center;
    gap: 1rem;
  }

  .way > .service-block-two {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 20rem;
  }

  .way > .service-block-two > .inner-box > h3 > a {
    color: #f68e26;
  }

  .service-block-two > .inner-box > h3 {
    text-align: center;
    margin-bottom: 0px;
  }

  .way .block-shadow::after {
    background-color: #030100;
  }

  .way .block-shadow::before {
    background-color: #fc7a3a;
  }

  @media only screen and (max-width: 480px) {
    .way {
      margin: 0.5rem;
    }
    .way > .service-block-two {
      width: 100%;
      margin-bottom: 10px;
    }
  }
</style>
