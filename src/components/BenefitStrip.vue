<script setup>
import { ref } from "vue";

const isPaused = ref(false);

const benefits = [
  "LENGKAP PILIHANNYA",
  "BANYAK UKURANNYA",
  "BERSAHABAT HARGANYA",
  "PRAKTIS BUAT USAHA",
  "PAS BUAT RUMAHAN",
  "KATO: KANTONGNYA PANTANG JEBOL",
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
          <li v-for="benefit in benefits" :key="benefit" class="benefit-item">
            <span class="benefit-text">{{ benefit }}</span>
            <svg class="benefit-sep" viewBox="0 0 24 24" fill="none" aria-hidden="true">
              <path d="M12 3v6M12 15v6M3 12h6M15 12h6" />
            </svg>
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
  padding: 20px 0;
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
  animation: benefit-scroll calc(var(--benefit-count) * 6s) linear infinite;
}

.benefit-track.is-paused { animation-play-state: paused; }

.benefit-list {
  display: flex;
  align-items: center;
  flex: 0 0 auto;
  min-width: 100vw;
  margin: 0;
  padding: 0;
  list-style: none;
}

.benefit-item {
  display: flex;
  align-items: center;
  flex: 1 0 auto;
  gap: clamp(20px, 2.5vw, 36px);
  padding-inline: clamp(20px, 2.5vw, 36px);
  white-space: nowrap;
}

.benefit-text {
  font-family: "Outfit", sans-serif;
  font-size: 17px;
  font-weight: 600;
  letter-spacing: 0.3px;
  text-transform: uppercase;
}

.benefit-sep {
  flex-shrink: 0;
  width: 14px;
  height: 14px;
  stroke: #a16f28;
  stroke-width: 1.5;
  stroke-linecap: round;
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
  .benefit-track { animation-duration: calc(var(--benefit-count) * 5s); }

  .benefit-item {
    gap: 16px;
    padding-inline: 16px;
  }

  .benefit-text { font-size: 14px; }
}

@media (prefers-reduced-motion: reduce) {
  .benefit-strip { padding-inline: var(--gutter); }
  .benefit-viewport { overflow: visible; }
  .benefit-track {
    width: auto;
    animation: none;
  }

  .benefit-list {
    flex-wrap: wrap;
    justify-content: center;
    width: 100%;
    min-width: 0;
    row-gap: 12px;
  }

  .benefit-list[aria-hidden="true"],
  .benefit-toggle { display: none; }

  .benefit-item {
    padding: 0;
    white-space: normal;
  }

  .benefit-item:last-child .benefit-sep { display: none; }
}
</style>
