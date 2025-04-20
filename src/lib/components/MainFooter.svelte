<script lang="ts">
  import { currentMenuActive } from "$lib/stores.svelte";
  import { footer as footerData, contact } from "$lib/data";
  import ButtonJoin from "./ButtonJoin.svelte";
  import { base } from "$app/paths";

  function formatPhoneNumber(phoneNumber: string) {
    return phoneNumber.replace(/(\d{2})(\d{3})(\d{3})(\d{4})/, "$1-$2-$3-$4");
  }

  const phoneNumberFormatted = formatPhoneNumber(footerData.phone_number);
</script>

<!-- main-footer -->
<footer class="main-footer">
  <div class="footer-top p_relative">
    <div class="bg-color bg-color-1"></div>
    <div class="auto-container">
      <div class="inner-container">
        <div class="row align-items-center">
          <div class="col-lg-6 col-md-12 col-sm-12 logo-column">
            <figure class="footer-logo">
              <a href={`${base}`} onclick={() => (currentMenuActive.current = "")}><img src={footerData.logo_path} alt="logo" /></a>
            </figure>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="main-footer-content p_relative bg-color-1">
    <div class="widget-section p_relative pt_90 pb_90">
      <div class="auto-container">
        <div class="row clearfix">
          <div class="col-lg-6 col-md-12 col-sm-12 footer-column">
            <div class="footer-widget about-widget">
              <div class="widget-content">
                <h2>{@html footerData.title}</h2>
                <ButtonJoin phoneNumber={footerData.phone_number} buttonText={footerData.button_text} defaultMessage={footerData.button_default_message} />
              </div>
            </div>
          </div>
          <div class="col-lg-3 col-md-6 col-sm-12 footer-column">
            <div class="footer-widget links-widget">
              <div class="widget-title">
                <h3>Links</h3>
              </div>
              <div class="widget-content">
                <ul class="links-list clearfix">
                  <li>
                    <a
                      href={`${base}`}
                      aria-label="Beranda"
                      onclick={() => {
                        currentMenuActive.current = "";
                      }}>Beranda</a
                    >
                  </li>
                  <li>
                    <a
                      href="{`${base}/#about`}"
                      onclick={() => {
                        currentMenuActive.current = "about";
                      }}>Tentang Kami</a
                    >
                  </li>
                  <li>
                    <a
                      href={`${base}/tabungan-umroh`}
                      onclick={() => {
                        currentMenuActive.current = "tabungan-umroh";
                      }}>Tabungan Umroh</a
                    >
                  </li>
                  <li>
                    <a
                      href={`${base}/promo`}
                      onclick={() => {
                        currentMenuActive.current = "promo";
                      }}>Promo</a
                    >
                  </li>
                </ul>
              </div>
            </div>
          </div>
          <div class="col-lg-3 col-md-6 col-sm-12 footer-column">
            <div class="footer-widget contact-widget">
              <div class="widget-title">
                <h3>{contact.title}</h3>
              </div>
              <div class="widget-content">
                <ul class="info-list mb_25">
                  <li>
                    <i class="icon-9"></i><span
                      >Alamat: {contact.address}</span
                    >
                  </li>
                  <li>
                    <i class="icon-10"></i><span
                      >Email: <a href={undefined}>{contact.email}</a
                      ></span
                    >
                  </li>
                  <li>
                    <i class="icon-11"></i><span
                        >Telp: <a
                        href={`https://wa.me/${contact.phone_number}?text=${footerData.button_default_message}`}
                        >+{formatPhoneNumber(contact.phone_number)}</a
                    ></span
                    >
                  </li>
                  <li>
                    <i class="icon-11"></i><span
                        >Alternatif: <a
                        href={`https://wa.me/${contact.phone_number_alternative}?text=${footerData.button_default_message}`}
                    >+{formatPhoneNumber(contact.phone_number_alternative)}</a
                    ></span
                    >
                  </li>
                </ul>
                <ul class="social-links">
                  <li>
                    <a href={undefined} aria-label="socmed"
                      ><i class="icon-12"></i></a
                    >
                  </li>
                  <li>
                    <a href={undefined} aria-label="socmed"
                      ><i class="icon-13"></i></a
                    >
                  </li>
                  <li>
                    <a href={undefined} aria-label="socmed"
                      ><i class="icon-14"></i></a
                    >
                  </li>
                  <li>
                    <a href={undefined} aria-label="socmed"
                      ><i class="icon-15"></i></a
                    >
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="footer-bottom">
      <div class="auto-container">
        <div class="bottom-inner">
          <div class="copyright">
            <p>
              Copyright 2025 by <a href={undefined}>MIT</a> All Right Reserved.
            </p>
          </div>
          <!-- <ul class="footer-menu">
                                <li><a href="index.html">Home</a></li>
                                <li><a href="about.html">About Us</a></li>
                                <li><a href="team.html">Team</a></li>
                                <li><a href="blog.html">Blog</a></li>
                                <li><a href="contact.html">Contact</a></li>
                            </ul> -->
        </div>
      </div>
    </div>
  </div>
</footer>

<!-- main-footer end -->
<style>
  .bottom-inner {
    justify-content: center;
  }
</style>
