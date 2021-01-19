<template>
  <div class="default-nuxt">
    <header>
      <div class="header-container">
        <div class="header-left">
          <a href="/">
            <img src="@/assets/image/logo.png" alt="SMART CHOICES" class="logo">
          </a>
          <p class="text">Improve Your Hair, Skin and Sleep</p>
        </div>
        <a href="/" class="btn">Silk Pillowcase</a>
      </div>
      
    </header>
    <main>
      <Nuxt />
    </main>
    <footer>
      <div class="footer-container">
        <a href="/" rel="noopener noreferrer">
            <img src="@/assets/image/footerLogo.png" alt="SMART CHOICES" class="footer-logo">
        </a> 
        <div class="content">
            <p>MARKETING DISCLOSURE: This website is a market place. As such you should know that the owner has a monetary connection to the product and services advertised on the site.</p>
            <p>The owner receives payment whenever a qualified lead is referred but that is the extent of it.</p>
            <p>ADVERTISING DISCLOSURE: This website and the products & services referred to on the site are advertising marketplaces.This website is an advertisement and note a news publication.Any photographs of persons used on thissite are models. The owner of this site and of the products and services referred to on this site only provides a service whereconsumers can obtain and compare.</p>
            <p>2020 All Rights Reserved.</p>
        </div>
        <ul class="footer-nav-list">
            <li>
                <nuxt-link to="/disclosure">Disclosure</nuxt-link>
            </li>
            <li>
                <nuxt-link to="/privacy">Privacy Policy</nuxt-link>
            </li>
            <li>
                <nuxt-link to="/terms">Terms of Use</nuxt-link>
            </li>
            <li>
                <nuxt-link to="/about">About Us</nuxt-link>
            </li>
            <li>
                <nuxt-link to="/contact">Contact Us</nuxt-link>
            </li>
        </ul>
      </div>
    </footer>
  </div>
</template>

<style lang="scss" scoped>
@import '~/assets/scss/default.scss';
</style>
