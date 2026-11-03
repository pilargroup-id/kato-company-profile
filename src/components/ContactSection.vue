<script setup>
const whatsapp = {
  number: "081190057235",
  href: "https://wa.me/6281190057235",
};

const linkGroups = [
  {
    title: "Follow Us",
    id: "contact-socials",
    links: [
      { name: "Instagram", detail: "@kato.factory", icon: "instagram", href: "https://www.instagram.com/kato.factory/" },
      { name: "TikTok", detail: "@kato.factory", icon: "tiktok", href: "https://www.tiktok.com/@kato.factory" },
      { name: "Facebook", detail: "KATO Factory", icon: "facebook", href: "https://www.facebook.com/profile.php?id=61591586348161" },
    ],
  },
];
</script>

<template>
  <section id="contact" class="contact-us" aria-labelledby="contact-title">
    <div class="contact-us__inner">
      <header class="contact-us__heading">
        <h2 id="contact-title">Contact Us<span aria-hidden="true">.</span></h2>
        <span class="contact-us__logo">
          <img
            src="/assets/Logo-KATO1.svg"
            alt="KATO"
            width="1080"
            height="1080"
            loading="lazy"
          />
        </span>
      </header>

      <a
        class="contact-us__whatsapp"
        :href="whatsapp.href"
        target="_blank"
        rel="noopener noreferrer"
        :aria-label="`WhatsApp KATO ${whatsapp.number} (buka tab baru)`"
      >
        <span class="contact-us__whatsapp-badge">
          <img src="/assets/platforms/whatsapp.svg" alt="" width="14" height="14" loading="lazy" />
        </span>
        {{ whatsapp.number }}
      </a>

      <div class="contact-us__columns">
        <nav
          v-for="group in linkGroups"
          :key="group.id"
          class="contact-us__group"
          :aria-labelledby="group.id"
        >
          <h3 :id="group.id">{{ group.title }}</h3>
          <ul class="contact-us__links">
            <li v-for="link in group.links" :key="link.name">
              <a
                class="contact-us__link"
                :href="link.href"
                target="_blank"
                rel="noopener noreferrer"
                :aria-label="`${link.name} KATO (buka tab baru)`"
              >
                <img
                  class="contact-us__icon"
                  :src="`/assets/platforms/${link.icon}.svg`"
                  alt=""
                  width="20"
                  height="20"
                  loading="lazy"
                />
                <span class="contact-us__link-copy">
                  <span class="contact-us__platform">{{ link.name }}</span>
                  <span class="contact-us__handle">{{ link.detail }}</span>
                </span>
                <svg class="contact-us__arrow" viewBox="0 0 24 24" fill="none" aria-hidden="true">
                  <path d="M6 18 18 6M6 6h12v12" />
                </svg>
              </a>
            </li>
          </ul>
        </nav>

        <div class="contact-us__details">
          <h3>Alamat</h3>
          <div class="contact-us__address">
            <svg class="contact-us__pin" viewBox="0 0 24 24" fill="none" aria-hidden="true">
              <path d="M19 10c0 5-7 11-7 11S5 15 5 10a7 7 0 1 1 14 0Z" />
              <circle cx="12" cy="10" r="2.5" />
            </svg>
            <address>
              Komplek Ruko Duta Garden Blok B4 nomor: 08–09, Kelurahan Jurumudi Baru,
              Kec. Benda, Kota Tangerang, Banten, Kode Pos: 15124
            </address>
          </div>
        </div>
      </div>

      <p class="contact-us__copyright">
        <small>© 2026 KATO. All rights reserved.</small>
      </p>
    </div>
  </section>
</template>

<style scoped>
.contact-us {
  padding: 32px var(--gutter, 5.5%) 24px;
  scroll-margin-top: 88px;
  background: #f4f1e9;
  color: #35473d;
}
.contact-us__inner {
  max-width: 1240px;
  margin-inline: auto;
}
.contact-us__heading {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 32px;
  padding-bottom: 16px;
  border-bottom: 1px solid #dcded4;
}
.contact-us h2 {
  margin: 0;
  font: 600 clamp(28px, 3vw, 36px)/1.1 "Outfit", sans-serif;
  letter-spacing: -1px;
}
.contact-us h2 > span {
  color: #d8a039;
}
.contact-us__logo {
  position: relative;
  display: block;
  flex-shrink: 0;
  width: 100px;
  aspect-ratio: 840 / 220;
  overflow: hidden;
}
.contact-us__logo img {
  position: absolute;
  top: 50%;
  left: 50%;
  /* Crop the square SVG's empty margins without stretching the artwork. */
  width: calc(100% * 1080 / 840);
  height: auto;
  transform: translate(-50%, -50%);
}
.contact-us__whatsapp {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  min-height: 44px;
  margin-top: 12px;
  color: #526157;
  font-size: 13px;
  letter-spacing: 0.2px;
  transition: color 0.2s;
}
.contact-us__whatsapp-badge {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  flex: 0 0 24px;
  width: 24px;
  height: 24px;
  border-radius: 50%;
  background: #3f8a5a;
}
.contact-us__whatsapp-badge img {
  display: block;
  filter: brightness(0) invert(1);
}
.contact-us__whatsapp:hover {
  color: #856020;
}
.contact-us__columns {
  display: grid;
  grid-template-columns: minmax(0, 7fr) minmax(0, 5fr);
  align-items: start;
  gap: clamp(32px, 5vw, 64px);
  padding-top: 12px;
}
.contact-us__columns > * {
  min-width: 0;
}
.contact-us h3 {
  margin: 0 0 8px;
  font: 500 16px/1.4 "Outfit", sans-serif;
}
.contact-us__link,
.contact-us__address {
  display: flex;
  align-items: center;
  gap: 10px;
}
.contact-us__icon,
.contact-us__pin {
  display: block;
  flex: 0 0 20px;
  width: 20px;
  height: 20px;
}
.contact-us__icon {
  object-fit: contain;
  filter: brightness(0);
  opacity: 0.72;
}
.contact-us__platform,
.contact-us__handle {
  display: block;
}
.contact-us__handle {
  color: #626d64;
  font-size: 11px;
  line-height: 1.5;
}
.contact-us__address {
  align-items: flex-start;
  padding-top: 4px;
}
.contact-us__pin {
  margin-top: 2px;
  stroke: #626d64;
  stroke-width: 1.5;
  stroke-linecap: round;
  stroke-linejoin: round;
}
.contact-us address {
  margin: 0;
  color: #526157;
  font-size: 13px;
  font-style: normal;
  line-height: 1.7;
}
.contact-us__links {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 170px));
  gap: 12px clamp(24px, 4vw, 48px);
  margin: 0;
  padding: 0;
  list-style: none;
}
.contact-us__link {
  min-height: 52px;
  padding: 6px 0 8px;
  border-bottom: 1px solid #cfd2c6;
}
.contact-us__link-copy {
  min-width: 0;
}
.contact-us__platform {
  font-size: 13px;
  font-weight: 500;
  line-height: 1.5;
}
.contact-us__handle {
  margin-top: 2px;
  overflow-wrap: anywhere;
}
.contact-us__arrow {
  flex: 0 0 14px;
  width: 14px;
  height: 14px;
  margin-left: auto;
  color: #6c786e;
  stroke: currentColor;
  stroke-width: 1.5;
  stroke-linecap: round;
  stroke-linejoin: round;
  transition: color 0.2s;
}
.contact-us__copyright {
  margin: 24px 0 0;
  padding-top: 20px;
  border-top: 1px solid #dcded4;
  color: #35473d;
  font-size: 12px;
  line-height: 1.5;
  text-align: center;
}
.contact-us__copyright small {
  font-size: inherit;
}
.contact-us a {
  border-radius: 2px;
}
.contact-us a:hover .contact-us__platform,
.contact-us a:hover .contact-us__arrow {
  color: #856020;
}
.contact-us a:hover.contact-us__link {
  border-bottom-color: #856020;
}
.contact-us a:focus-visible {
  outline: 2px solid #856020;
  outline-offset: 6px;
}
@media (max-width: 760px) {
  .contact-us {
    padding: 28px 6% 20px;
    scroll-margin-top: 72px;
  }
  .contact-us__heading {
    gap: 20px;
  }
  .contact-us__logo {
    width: 80px;
  }
  .contact-us__columns {
    grid-template-columns: 1fr;
    gap: 24px;
  }
  .contact-us__links {
    grid-template-columns: repeat(3, minmax(0, 1fr));
    column-gap: 20px;
  }
}
@media (max-width: 480px) {
  .contact-us__heading {
    gap: 16px;
  }
  .contact-us__logo {
    width: 72px;
  }
  .contact-us__links {
    grid-template-columns: 1fr;
    row-gap: 0;
  }
}
</style>
