<template>
  <footer class="footer">
    <a href="#home" class="footer-brand" aria-label="KATO beranda">
      <img src="/assets/Logo-KATO1.svg" alt="KATO" width="1080" height="1080" loading="lazy" />
    </a>
    <p>Solusi kantong dan kemasan untuk setiap kebutuhan.</p>
    <div class="footer-links">
      <a href="#about">Tentang</a><a href="#contact">Kontak</a>
    </div>
    <span>© 2026 KATO. All rights reserved.</span>
  </footer>
</template>

<style scoped>
.footer-brand {
  position: relative;
  display: block;
  flex-shrink: 0;
  width: 100px;
  aspect-ratio: 840 / 220;
  overflow: hidden;
}
.footer-brand img {
  position: absolute;
  top: 50%;
  left: 50%;
  /* Crop the square SVG's empty margins without stretching the artwork. */
  width: calc(100% * 1080 / 840);
  height: auto;
  transform: translate(-50%, -50%);
}
.footer-brand:focus-visible {
  outline: 2px solid #856020;
  outline-offset: 6px;
}
@media (max-width: 760px) {
  .footer-brand {
    width: 80px;
  }
}
</style>
