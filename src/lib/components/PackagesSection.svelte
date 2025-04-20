<script>
  import { umrohPackage } from "$lib/data";
  import ButtonJoin from "./ButtonJoin.svelte";
</script>

<!-- project-style-four -->
<section class="project-style-four pt_140 pb_150 bg-color-1">
  <div class="auto-container">
    <div class="sec-title centred light mb_70">
      <span class="sub-title gradient-color">{umrohPackage.section_title}</span>
      <h2>{@html umrohPackage.title}</h2>
    </div>
    <div class="inner-container">
      {#each umrohPackage.lists as item, i}
        <div class="project-block-four pr_5 pb_5 block-shadow">
          <div class="inner-box">
            <span class="count-text">{i < 10 ? `0${i + 1}` : i + 1}</span>
            <h3><a href={undefined}>{item.name}</a></h3>
            <ul class="category-list">
              <!-- <li><a href="project-details.html">Design</a></li>
                                    <li><a href="project-details.html">Development</a></li> -->
            </ul>
            <div class="link">
              <a href={item.link} target="_blank" aria-label="package"
                ><i class="icon-3"></i></a
              >
            </div>
            <figure class="image-box">
              <img src={item.image_path} alt="" />
            </figure>
          </div>
        </div>
      {/each}
    </div>
    <div class="more-btn centred pt_50">
      <ButtonJoin
        phoneNumber={umrohPackage.phone_number}
        buttonText={umrohPackage.button_text}
        defaultMessage={umrohPackage.button_default_message}
      />
    </div>
  </div>
</section>
<!-- project-style-four end -->
