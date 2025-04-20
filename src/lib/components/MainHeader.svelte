<script>
  // @ts-nocheck
  import { header as headerData, contact, header } from "$lib/data";
  import { fade, fly } from "svelte/transition";
  import { currentMenuActive } from "$lib/stores.svelte.js";
  import { base } from "$app/paths";
  let { pageYOffset } = $props();

  let showMobileMenu = $state(false);

  $effect(() => {
    if (showMobileMenu) {
      document.body.classList.add("mobile-menu-visible");
    } else {
      document.body.classList.remove("mobile-menu-visible");
    }
  });

  function formatPhoneNumber(phoneNumber) {
    return phoneNumber.replace(/(\d{2})(\d{3})(\d{3})(\d{4})/, "$1-$2-$3-$4");
  }

  const phoneNumberFormatted = formatPhoneNumber(headerData.phone_number);
</script>

<!-- main header -->
<!-- svelte-ignore component_name_lowercase -->
<header class="main-header {pageYOffset > 150 ? 'fixed-header' : ''}">
  <!-- header-lower -->
  <div class="header-lower">
    <div class="outer-container p_relative pl_70 pr_70">
      <div class="outer-box">
        <div class="left-column">
          <figure class="logo-box">
            <a href="/" onclick={() => (currentMenuActive.current = "")}><img src={headerData.logo_path} alt="" /></a>
          </figure>
          <div class="menu-area">
            <!--Mobile Navigation Toggler-->
            <a
              href={undefined}
              onclick={() => (showMobileMenu = !showMobileMenu)}
              aria-label="mobile-menu"
            >
              <div class="mobile-nav-toggler">
                <i class="icon-bar"></i>
                <i class="icon-bar"></i>
                <i class="icon-bar"></i>
              </div>
            </a>
            <nav class="main-menu navbar-expand-md navbar-light clearfix">
              <div
                class="collapse navbar-collapse show clearfix"
                id="navbarSupportedContent"
              >
                <ul class="navigation clearfix">
                  <li class:current={currentMenuActive.current == ""}>
                    <a href={`${base}`} onclick={() => (currentMenuActive.current = "")}
                      >Beranda</a
                    >
                  </li>
                  <li class:current={currentMenuActive.current == "about"}>
                    <a
                      href={`${base}/#about`}
                      onclick={() => (currentMenuActive.current = "about")}
                      >Tentang Kami</a
                    >
                  </li>
                  <li
                    class:current={currentMenuActive.current ==
                      "tabungan-umroh"}
                  >
                    <a
                      href={`${base}/tabungan-umroh`}
                      onclick={() =>
                        (currentMenuActive.current = "tabungan-umroh")}
                      >Tabungan Umroh</a
                    >
                  </li>
                  <li class:current={currentMenuActive.current == "promo"}>
                    <a
                      href={`${base}/promo`}
                      onclick={() => (currentMenuActive.current = "promo")}
                      >Promo</a
                    >
                  </li>
                </ul>
              </div>
            </nav>
          </div>
        </div>
        <div class="menu-right-content">
          <div class="support-box">
            <a
              href={`https://wa.me/${headerData.phone_number}?text=${headerData.button_default_message}`}
              ><i class="icon-1"></i>
              <span>+{formatPhoneNumber(headerData.phone_number)}</span></a
            >
          </div>
          <div class="btn-box">
            <a
              href={`https://wa.me/${headerData.phone_number}?text=${headerData.button_default_message}`}
              class="theme-btn btn-one"
              ><span class="text">{headerData.button_text}</span></a
            >
          </div>
        </div>
      </div>
    </div>
  </div>

  <!--sticky Header-->
  <div class="sticky-header">
    <div class="outer-container p_relative pl_70 pr_70">
      <div class="outer-box">
        <div class="left-column">
          <figure class="logo-box">
            <a href={`${base}`} onclick={() => (currentMenuActive.current = "")}><img src={headerData.logo_path} alt="logo" /></a>
          </figure>
          <div class="menu-area">
            <nav class="main-menu clearfix">
              {#if pageYOffset}
                <div
                  class="collapse navbar-collapse show clearfix"
                  id="navbarSupportedContent"
                  in:fly={{ y: -200, duration: 1000 }}
                  out:fade
                >
                  <ul class="navigation clearfix">
                    <li class:current={currentMenuActive.current == ""}>
                      <a
                        href={`${base}`}
                        onclick={() => (currentMenuActive.current = "")}
                        >Beranda</a
                      >
                    </li>
                    <li class:current={currentMenuActive.current == "about"}>
                      <a
                        href={`${base}/#about`}
                        onclick={() => (currentMenuActive.current = "about")}
                        >Tentang Kami</a
                      >
                    </li>
                    <li
                      class:current={currentMenuActive.current ==
                        "tabungan-umroh"}
                    >
                      <a
                        href={`${base}/tabungan-umroh`}
                        onclick={() =>
                          (currentMenuActive.current = "tabungan-umroh")}
                        >Tabungan Umroh</a
                      >
                    </li>
                    <li class:current={currentMenuActive.current == "promo"}>
                      <a
                        href={`${base}/promo`}
                        onclick={() => (currentMenuActive.current = "promo")}
                        >Promo</a
                      >
                    </li>
                  </ul>
                </div>
              {/if}
            </nav>
          </div>
        </div>
        <div class="menu-right-content">
          <div class="support-box">
            <a
              href={`https://wa.me/${headerData.phone_number}?text=${headerData.button_default_message}`}
              ><i class="icon-1"></i>
              <span>+{formatPhoneNumber(headerData.phone_number)}</span></a
            >
          </div>
          <div class="btn-box">
            <a
              href={`https://wa.me/${headerData.phone_number}?text=${headerData.button_default_message}`}
              class="theme-btn btn-one"
              ><span class="text">{headerData.button_text}</span></a
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</header>
<!-- main-header end -->

<!-- Mobile Menu  -->
<div class="mobile-menu">
  <div class="menu-backdrop"></div>
  <a
    href={undefined}
    aria-label="close"
    onclick={() => showMobileMenu = !showMobileMenu}
    ><div class="close-btn"><i class="fas fa-times"></i></div></a
  >
  <nav class="menu-box">
    <div class="nav-logo">
      <a href={`${base}`} onclick={() => (currentMenuActive.current = "")}
        ><img src="{headerData.logo_path}" alt="logo" title="" /></a
      >
    </div>
    <div class="menu-outer">
      {#if showMobileMenu}
        <div
          class="collapse navbar-collapse show clearfix"
          id="navbarSupportedContent"
          in:fly={{ y: -200, duration: 1000 }}
          out:fade
        >
          <ul class="navigation clearfix">
            <li class:current={currentMenuActive.current == ""}>
              <a
                href={`${base}`}
                onclick={() => {
                  showMobileMenu = !showMobileMenu;
                  currentMenuActive.current = "";
                }}>Beranda</a
              >
            </li>
            <li class:current={currentMenuActive.current == "about"}>
              <a
                href={`${base}/#about`}
                onclick={() => {
                  showMobileMenu = !showMobileMenu;
                  currentMenuActive.current = "about";
                }}>Tentang Kami</a
              >
            </li>
            <li class:current={currentMenuActive.current == "tabungan-umroh"}>
              <a
                href={`${base}/tabungan-umroh`}
                onclick={() => {
                  showMobileMenu = !showMobileMenu;
                  currentMenuActive.current = "tabungan-umroh";
                }}>Tabungan Umroh</a
              >
            </li>
            <li class:current={currentMenuActive.current == "promo"}>
              <a
                href={`${base}/promo`}
                onclick={() => {
                  showMobileMenu = !showMobileMenu;
                  currentMenuActive.current = "promo";
                }}>Promo</a
              >
            </li>
          </ul>
        </div>
      {/if}
    </div>
    <div class="contact-info">
      <h4>{contact.title}</h4>
      <ul>
        <li>
          <i class="icon-9"></i><span
            >Alamat: {contact.address}</span
          >
        </li>
        <li>
          <i class="icon-10"></i><span
            >Email: <a href={undefined}>{contact.email}</a></span
          >
        </li>
        <li>
          <i class="icon-11"></i><span
            >Telp: <a
              href={`https://wa.me/${contact.phone_number}?text=${headerData.button_default_message}`}
              >+{formatPhoneNumber(contact.phone_number)}</a
            ></span
          >
        </li>
        <li>
          <i class="icon-11"></i><span
            >Alternatif: <a
                href={`https://wa.me/${contact.phone_number_alternative}?text=${headerData.button_default_message}`}
              >+{formatPhoneNumber(contact.phone_number_alternative)}</a
            ></span
          >
        </li>
      </ul>
    </div>
    <!-- <div class="social-links">
                    <ul class="clearfix">
                        <li><a href="index.html"><span class="fab fa-twitter"></span></a></li>
                        <li><a href="index.html"><span class="fab fa-facebook-square"></span></a></li>
                        <li><a href="index.html"><span class="fab fa-pinterest-p"></span></a></li>
                        <li><a href="index.html"><span class="fab fa-instagram"></span></a></li>
                        <li><a href="index.html"><span class="fab fa-youtube"></span></a></li>
                    </ul>
                </div> -->
  </nav>
</div>
<!-- End Mobile Menu -->

<style>
    a:has(img) {
        display: flex;
    }
</style>