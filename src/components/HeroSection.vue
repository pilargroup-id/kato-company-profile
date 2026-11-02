<script setup>
const heroImages = [
  {
    src: "/assets/main-image-1.jpg",
    alt: "Kantong sampah hitam untuk kebersihan rumah dan usaha",
    width: 1080,
    height: 1920,
  },
  {
    src: "/assets/main-image-2.jpg",
    alt: "Kantong bening berisi sayuran dan buah segar",
    width: 1080,
    height: 1080,
  },
  {
    src: "/assets/main-image-3.jpg",
    alt: "Kantong belanja hitam berisi sayuran segar",
    width: 1080,
    height: 1080,
  },
];
</script>

<template>
  <section id="home" class="kato-hero" aria-labelledby="hero-title">
    <div class="kato-hero__layout">
      <div class="kato-hero__copy">
        <p class="kato-hero__eyebrow">KANTONG UNTUK RUMAH &amp; USAHA</p>
        <h1 id="hero-title" class="kato-hero__title">
          <span class="kato-hero__sr-only">KATO: </span>
          <span class="kato-hero__title-line">
            <span class="kato-hero__logo" aria-hidden="true">
              <img src="/assets/Logo-KATO1.svg" alt="" width="1080" height="1080" />
            </span>
            <span>Kantongnya</span>
          </span>
          <span>Pantang Jebol!</span>
        </h1>
        <p class="kato-hero__description">
          Dari urusan dapur hingga kebutuhan usaha, temukan kantong yang tepat.
          Pilihan bahan dan ukuran lengkap untuk setiap aktivitas Anda.
        </p>
        <div class="kato-hero__actions">
          <a href="https://shopee.co.id/katofactory" class="kato-hero__primary">
            Beli Sekarang
            <!-- <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
              <path d="M5 12h14m-6-6 6 6-6 6" />
            </svg> -->
          </a>
          <a href="#contact" class="kato-hero__secondary">Tanya Pemesanan</a>
        </div>
        <div class="kato-hero__details">
          <p class="kato-hero__details-title">Untuk aktivitas sehari-hari</p>
          <p>
            Rumah tangga <span aria-hidden="true">/</span> Kuliner
            <span aria-hidden="true">/</span> Laundry
            <span aria-hidden="true">/</span> Retail
          </p>
        </div>
      </div>

      <div class="kato-hero__showcase">
        <div class="kato-hero__showcase-heading">
          <span>KENALI PILIHAN KATO</span>
        </div>
        <div class="kato-hero__collage">
          <div class="kato-hero__collage-panel">
            <figure
              v-for="(image, index) in heroImages"
              :key="image.src"
              class="kato-hero__card"
              :class="{ 'kato-hero__card--main': index === 0 }"
            >
              <img
                :src="image.src"
                :alt="image.alt"
                :width="image.width"
                :height="image.height"
                :fetchpriority="index === 0 ? 'high' : 'auto'"
                class="kato-hero__card-image"
              />
              <span class="kato-hero__card-brand" aria-hidden="true">
                <span class="kato-hero__logo">
                  <img src="/assets/Logo-KATO1.svg" alt="" width="1080" height="1080" />
                </span>
              </span>
            </figure>
          </div>
        </div>
      </div>
    </div>
    <div class="kato-hero__footer">
      <span>PT KATO PIAGAM INDONESIA</span>
      <a href="#about">
        Lebih dekat dengan KATO
        <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
          <path d="M12 5v14m-6-6 6 6 6-6" />
        </svg>
      </a>
    </div>
  </section>
</template>

<style scoped>
.kato-hero {
  --hero-ink: #081e32;
  --hero-muted: #5e6b72;
  --hero-line: #dadeda;
  --hero-gold: #faa719;
  --hero-gold-light: #f3dfb0;
  padding: 88px max(5.5%, calc((100vw - 1400px) / 2)) 0;
  color: var(--hero-ink);
  background: #fafaf7;
}
.kato-hero__layout {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(0, 1.08fr);
  align-items: center;
  gap: clamp(40px, 6vw, 96px);
  max-width: 1400px;
  margin-inline: auto;
  padding-block: clamp(56px, 6vw, 88px) 64px;
}
.kato-hero__eyebrow {
  display: flex;
  align-items: center;
  gap: 12px;
  margin: 0 0 26px;
  color: #49635e;
  font-size: 10px;
  font-weight: 700;
  line-height: 1.6;
  letter-spacing: 1.8px;
}
.kato-hero__eyebrow::before {
  width: 26px;
  height: 2px;
  flex-shrink: 0;
  background: var(--hero-gold);
  content: "";
}
.kato-hero__title {
  margin: 0;
  font-family: "Outfit", sans-serif;
  font-size: clamp(46px, 4.7vw, 72px);
  font-weight: 650;
  line-height: 1.08;
  letter-spacing: -2.5px;
}
.kato-hero__title > span:last-child {
  color: var(--hero-gold);
}
.kato-hero__title-line {
  display: flex;
  align-items: center;
  gap: 0.2em;
  white-space: nowrap;
}
.kato-hero__logo {
  position: relative;
  display: block;
  width: 2.5em;
  height: 0.7em;
  flex-shrink: 0;
  overflow: hidden;
}
.kato-hero__logo img {
  position: absolute;
  top: 50%;
  left: 50%;
  /* Crop the empty margins in the square SVG without stretching the logo. */
  width: calc(100% * 1080 / 840);
  height: auto;
  transform: translate(-50%, -50%);
}
.kato-hero__description {
  max-width: 410px;
  margin: 26px 0 0;
  color: var(--hero-muted);
  font-size: 15px;
  line-height: 1.85;
}
.kato-hero__actions {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  gap: 16px 26px;
  margin-top: 30px;
}
.kato-hero__primary,
.kato-hero__secondary {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 50px;
  font-size: 13px;
  font-weight: 700;
}
.kato-hero__primary {
  gap: 22px;
  padding: 14px 22px;
  border: 1px solid var(--hero-ink);
  border-radius: 4px;
  background: var(--hero-ink);
  color: #fff;
  transition: background 180ms ease, border-color 180ms ease;
}
.kato-hero__primary:hover {
  border-color: #164c47;
  background: #164c47;
}
.kato-hero__secondary {
  text-decoration: underline;
  text-decoration-color: #a5afab;
  text-underline-offset: 6px;
  transition: text-decoration-color 180ms ease;
}
.kato-hero__secondary:hover { text-decoration-color: var(--hero-ink); }
.kato-hero svg {
  width: 18px;
  height: 18px;
  flex-shrink: 0;
  stroke: currentColor;
  stroke-width: 1.5;
  stroke-linecap: round;
  stroke-linejoin: round;
}
.kato-hero__details {
  margin-top: 42px;
  padding-top: 22px;
  border-top: 1px solid var(--hero-line);
}
.kato-hero__details p {
  margin: 0;
  color: var(--hero-muted);
  font-size: 11px;
  line-height: 1.9;
}
.kato-hero__details .kato-hero__details-title {
  margin-bottom: 5px;
  color: var(--hero-ink);
  font-size: 12px;
  font-weight: 600;
}
.kato-hero__details p > span {
  padding-inline: 7px;
  color: #a6afa9;
}
.kato-hero__showcase { min-width: 0; }
.kato-hero__showcase-heading {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  margin-bottom: 16px;
  font-size: 10px;
  font-weight: 600;
  letter-spacing: 1.5px;
}
.kato-hero__collage {
  position: relative;
  isolation: isolate;
}
.kato-hero__collage::before {
  position: absolute;
  z-index: -1;
  inset: -4% 34% -4% 43%;
  border-radius: 24px;
  background: var(--hero-gold);
  transform: skew(-10deg);
  pointer-events: none;
  content: "";
}
.kato-hero__collage-panel {
  display: grid;
  grid-template-columns: minmax(0, 1.15fr) minmax(0, 1fr);
  grid-template-rows: repeat(2, minmax(0, 1fr));
  gap: 14px;
  animation: hero-collage-reveal 850ms cubic-bezier(0.2, 0.7, 0.2, 1) both;
}
.kato-hero__card {
  --card-lift: -7px;
  --card-tilt: -0.45deg;
  position: relative;
  aspect-ratio: 1;
  min-width: 0;
  min-height: 0;
  margin: 0;
  overflow: hidden;
  border: 4px solid #fff;
  border-radius: 14px;
  background: #e9e6dd;
  box-shadow: 0 12px 28px #081e3224, 0 3px 8px #081e3214;
  animation: hero-card-float 8s ease-in-out infinite;
  transition: border-color 300ms ease, box-shadow 300ms ease;
}
.kato-hero__card:nth-child(2) {
  --card-lift: -10px;
  --card-tilt: 0.8deg;
  animation-duration: 7s;
  animation-delay: -2s;
}
.kato-hero__card:nth-child(3) {
  --card-lift: -6px;
  --card-tilt: -0.7deg;
  animation-duration: 7.6s;
  animation-delay: -4s;
}
.kato-hero__card--main {
  aspect-ratio: auto;
  grid-column: 1;
  grid-row: 1 / span 2;
}
.kato-hero__card::after {
  position: absolute;
  z-index: 1;
  inset: 0;
  background: linear-gradient(
    180deg,
    rgb(20 79 140 / 24%),
    rgb(20 79 140 / 8%) 55%,
    rgb(8 43 80 / 16%)
  );
  pointer-events: none;
  content: "";
}
.kato-hero__card-brand {
  position: absolute;
  z-index: 2;
  top: clamp(10px, 1.2vw, 18px);
  left: clamp(10px, 1.2vw, 18px);
  width: clamp(68px, 6.6vw, 98px);
  max-width: calc(100% - 20px);
  padding: clamp(7px, 0.65vw, 10px);
  border: 1px solid #ffffff99;
  border-radius: 6px;
  background: #ffffffeb;
  box-shadow: 0 3px 12px #081e3214;
  pointer-events: none;
  user-select: none;
}
.kato-hero__card-brand .kato-hero__logo {
  width: 100%;
  height: auto;
  aspect-ratio: 3.5;
}
.kato-hero__card-image {
  position: absolute;
  inset: 0;
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
  transition: transform 600ms cubic-bezier(0.2, 0.7, 0.2, 1);
}
@media (hover: hover) and (pointer: fine) {
  .kato-hero__collage:hover .kato-hero__card {
    animation-play-state: paused;
  }
  .kato-hero__card:hover {
    border-color: var(--hero-gold-light);
    box-shadow: 0 18px 36px #081e3229, 0 4px 12px #96601c1a;
  }
  .kato-hero__card:hover .kato-hero__card-image {
    transform: scale(1.045);
  }
}
@keyframes hero-collage-reveal {
  from {
    opacity: 0;
    transform: translateY(18px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
@keyframes hero-card-float {
  0%,
  100% {
    transform: translateY(0) rotate(0);
  }
  50% {
    transform: translateY(var(--card-lift)) rotate(var(--card-tilt));
  }
}
.kato-hero__footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
  max-width: 1400px;
  min-height: 65px;
  margin-inline: auto;
  padding-block: 18px;
  border-top: 1px solid var(--hero-line);
  color: var(--hero-muted);
  font-size: 11px;
}
.kato-hero__footer a {
  display: inline-flex;
  align-items: center;
  gap: 14px;
  min-height: 28px;
  color: var(--hero-ink);
}
.kato-hero a:focus-visible {
  outline: 2px solid #0e8e82;
  outline-offset: 5px;
}
.kato-hero__sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  overflow: hidden;
  clip-path: inset(50%);
  white-space: nowrap;
}
@media (min-width: 761px) and (max-width: 1100px) {
  .kato-hero__layout {
    gap: 34px;
    padding-block: 56px 48px;
  }
  .kato-hero__title {
    font-size: clamp(37px, 4.65vw, 51px);
    letter-spacing: -1.7px;
  }
  .kato-hero__actions { gap: 10px 18px; }
  .kato-hero__primary {
    gap: 14px;
    padding-inline: 16px;
  }
}
@media (max-width: 760px) {
  .kato-hero { padding: 72px 6% 0; }
  .kato-hero__layout {
    grid-template-columns: minmax(0, 1fr);
    gap: 40px;
    padding-block: 46px 32px;
  }
  .kato-hero__eyebrow {
    gap: 10px;
    margin-bottom: 20px;
    font-size: 9px;
    letter-spacing: 1.4px;
  }
  .kato-hero__title {
    font-size: clamp(38px, 9vw, 62px);
    letter-spacing: -1.6px;
  }
  .kato-hero__description {
    margin-top: 20px;
    font-size: 14px;
    line-height: 1.8;
  }
  .kato-hero__actions {
    gap: 10px 22px;
    margin-top: 24px;
  }
  .kato-hero__details {
    margin-top: 28px;
    padding-top: 18px;
  }
  .kato-hero__collage-panel { gap: 10px; }
  .kato-hero__card { border-width: 3px; border-radius: 12px; }
  .kato-hero__footer { min-height: 60px; }
  .kato-hero__footer > span { display: none; }
  .kato-hero__footer a {
    justify-content: space-between;
    width: 100%;
  }
}
@media (max-width: 360px) {
  .kato-hero__title { font-size: 34px; }
  .kato-hero__primary,
  .kato-hero__secondary { font-size: 12px; }
  .kato-hero__primary {
    gap: 14px;
    padding-inline: 16px;
  }
  .kato-hero__details p > span { padding-inline: 4px; }
}
@media (prefers-reduced-motion: reduce) {
  .kato-hero__collage-panel,
  .kato-hero__card {
    animation: none;
    transform: none;
  }
  .kato-hero__card,
  .kato-hero__card-image {
    transition: none;
  }
  .kato-hero__card:hover .kato-hero__card-image {
    transform: none;
  }
}
</style>
