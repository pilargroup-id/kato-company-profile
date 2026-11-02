<script setup>
import { ref } from "vue";

const isPaused = ref(false);

const benefits = [
  {
    title: "Bahan berkualitas",
    description: "Kuat untuk pemakaian sehari-hari.",
    icon: "quality",
  },
  {
    title: "Harga lebih hemat",
    description: "Pilihan ekonomis untuk belanja rutin.",
    icon: "value",
  },
  {
    title: "Stok siap kirim",
    description: "Tersedia untuk kebutuhan harian Anda.",
    icon: "delivery",
  },
  {
    title: "Pilihan lengkap",
    description: "Beragam jenis, bahan, dan ukuran.",
    icon: "range",
  },
  {
    title: "Beragam ukuran",
    description: "Pilihan kecil hingga ukuran jumbo.",
    icon: "sizes",
  },
  {
    title: "Untuk rumah & usaha",
    description: "Dapur, laundry, hingga toko.",
    icon: "home",
  },
  {
    title: "Kantong serbaguna",
    description: "Untuk belanja, kemasan, dan kebersihan.",
    icon: "quality",
  },
  {
    title: "Toko online resmi",
    description: "Belanja di marketplace pilihan Anda.",
    icon: "shop",
  },
];
</script>

<template>
  <div class="benefit-strip" :style="{ '--benefit-count': benefits.length }">
    <div class="benefit-viewport">
      <div class="benefit-track" :class="{ 'is-paused': isPaused }">
        <ul
          v-for="group in 2"
          :key="group"
          class="benefit-list"
          :aria-label="group === 1 ? 'Keunggulan KATO' : undefined"
          :aria-hidden="group === 2 ? true : undefined"
          role="list"
        >
          <li v-for="benefit in benefits" :key="benefit.title" class="benefit-item">
            <svg class="benefit-icon" viewBox="0 0 32 32" fill="none" aria-hidden="true">
              <template v-if="benefit.icon === 'quality'">
                <path d="M7 10h18l2 18H5l2-18Z" />
                <path d="M12 11V7a4 4 0 0 1 8 0v4" />
                <path class="benefit-icon-accent" d="m11 20 3 3 7-7" />
              </template>
              <template v-else-if="benefit.icon === 'value'">
                <path d="M17 5H6v11l12 12 11-11L17 5Z" />
                <circle cx="11" cy="10" r="1.5" />
                <path class="benefit-icon-accent" d="m16 21 7-7" />
              </template>
              <template v-else-if="benefit.icon === 'delivery'">
                <path d="M4 22V7h16v15H12m8-10h5l4 6v4h-3" />
                <path d="M20 22h-1m4-10v6h6" />
                <circle cx="9" cy="23" r="3" />
                <circle cx="23" cy="23" r="3" />
                <path class="benefit-icon-accent" d="M2 12h8m-8 4h5" />
              </template>
              <template v-else-if="benefit.icon === 'sizes'">
                <path d="M4 15h9v13H4V15Zm15-3V4h9v24h-9" />
                <path class="benefit-icon-accent" d="M11 9h10v19H11V9Z" />
              </template>
              <template v-else-if="benefit.icon === 'home'">
                <path d="m3 14 13-10 13 10M6 12v16h20V12" />
                <path class="benefit-icon-accent" d="M13 28V18h6v10" />
              </template>
              <template v-else-if="benefit.icon === 'shop'">
                <path d="M6 14v14h20V14M8 4h16l4 9H4l4-9Z" />
                <path d="M4 13v2a4 4 0 0 0 8 0v-2m0 2a4 4 0 0 0 8 0v-2m0 2a4 4 0 0 0 8 0v-2" />
                <path class="benefit-icon-accent" d="M13 28v-8h6v8" />
              </template>
              <template v-else>
                <path d="m16 4 13 7-13 7L3 11l13-7Z" />
                <path d="m3 21 13 7 13-7" />
                <path class="benefit-icon-accent" d="m3 16 13 7 13-7" />
              </template>
            </svg>
            <div class="benefit-copy">
              <h3>{{ benefit.title }}</h3>
              <p>{{ benefit.description }}</p>
            </div>
          </li>
        </ul>
      </div>
    </div>
    <button
      class="benefit-toggle"
      type="button"
      :aria-label="isPaused ? 'Jalankan teks keunggulan' : 'Jeda teks keunggulan'"
      :title="isPaused ? 'Jalankan teks keunggulan' : 'Jeda teks keunggulan'"
      @click="isPaused = !isPaused"
    >
      <svg viewBox="0 0 20 20" fill="none" aria-hidden="true">
        <path v-if="isPaused" d="m7 4 9 6-9 6V4Z" />
        <path v-else d="M7 4v12m6-12v12" />
      </svg>
    </button>
  </div>
</template>

<style scoped>
.benefit-strip {
  position: relative;
  padding: 28px 0;
  border-block: 1px solid #dedbd1;
  background: #f0ede4;
  color: #081e32;
}

.benefit-viewport {
  width: 100%;
  overflow: hidden;
}

.benefit-track {
  display: flex;
  width: max-content;
  animation: benefit-scroll calc(var(--benefit-count) * 9s) linear infinite;
}

.benefit-track.is-paused { animation-play-state: paused; }

.benefit-list {
  display: flex;
  flex: 0 0 auto;
  min-width: 100vw;
  margin: 0;
  padding: 0;
  list-style: none;
}

.benefit-item {
  display: flex;
  align-items: flex-start;
  gap: 16px;
  flex: 1 0 auto;
  width: clamp(270px, 25vw, 380px);
  min-width: 0;
  padding: 4px clamp(28px, 3vw, 48px);
  border-right: 1px solid #d5d2c6;
}

.benefit-icon {
  width: 32px;
  height: 32px;
  flex-shrink: 0;
  margin-top: 2px;
  color: #344e45;
  stroke: currentColor;
  stroke-width: 1.5;
  stroke-linecap: round;
  stroke-linejoin: round;
}

.benefit-icon-accent { stroke: #a16f28; }
.benefit-copy { min-width: 0; }

.benefit-copy h3 {
  margin: 0;
  font-family: "Outfit", sans-serif;
  font-size: 17px;
  font-weight: 550;
  line-height: 1.35;
  letter-spacing: -0.2px;
}

.benefit-copy p {
  max-width: 22ch;
  margin: 7px 0 0;
  color: #5c665f;
  font-size: 12px;
  line-height: 1.65;
}

.benefit-toggle {
  position: absolute;
  right: 12px;
  bottom: 3px;
  display: grid;
  place-items: center;
  width: 24px;
  height: 24px;
  padding: 4px;
  border: 1px solid #c5c8bd;
  border-radius: 50%;
  background: transparent;
  color: #344e45;
  cursor: pointer;
}

.benefit-toggle:hover { background: #e5e2d8; }
.benefit-toggle:focus-visible {
  outline: 2px solid #344e45;
  outline-offset: 4px;
}

.benefit-toggle svg {
  width: 14px;
  height: 14px;
  stroke: currentColor;
  stroke-width: 1.5;
  stroke-linecap: round;
  stroke-linejoin: round;
}

@keyframes benefit-scroll {
  from { transform: translateX(0); }
  to { transform: translateX(-50%); }
}

@media (max-width: 760px) {
  .benefit-track { animation-duration: calc(var(--benefit-count) * 7s); }

  .benefit-item {
    gap: 12px;
    width: 270px;
    padding-inline: 24px;
  }

  .benefit-icon {
    width: 28px;
    height: 28px;
    margin-top: 0;
  }

  .benefit-copy h3 { font-size: 16px; }
  .benefit-copy p { margin-top: 6px; }
}

@media (prefers-reduced-motion: reduce) {
  .benefit-strip { padding-inline: var(--gutter); }
  .benefit-viewport { overflow: visible; }
  .benefit-track {
    width: auto;
    animation: none;
  }

  .benefit-list {
    display: grid;
    grid-template-columns: repeat(4, minmax(0, 1fr));
    width: 100%;
    min-width: 0;
    gap: 24px;
  }

  .benefit-list[aria-hidden="true"],
  .benefit-toggle { display: none; }

  .benefit-item {
    width: auto;
    padding: 0;
    border: 0;
  }
}

@media (prefers-reduced-motion: reduce) and (max-width: 1100px) {
  .benefit-list { grid-template-columns: repeat(2, minmax(0, 1fr)); }
}

@media (prefers-reduced-motion: reduce) and (max-width: 760px) {
  .benefit-item { flex-direction: column; }
}
</style>
