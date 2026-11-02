<template>
  <a
    class="floating-whatsapp"
    href="https://wa.me/6281190057235"
    target="_blank"
    rel="noopener noreferrer"
    aria-label="Chat dengan KATO melalui WhatsApp di 0811 9005 7235 (buka tab baru)"
    title="Chat WhatsApp KATO"
  >
    <img src="/assets/platforms/whatsapp.svg" alt="" width="28" height="28" />
  </a>
</template>

<style scoped>
.floating-whatsapp {
  position: fixed;
  right: calc(24px + env(safe-area-inset-right, 0px));
  bottom: calc(24px + env(safe-area-inset-bottom, 0px));
  z-index: 15;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 56px;
  height: 56px;
  padding: 13px;
  border: 1px solid #ffffff30;
  border-radius: 50%;
  background: #128044;
  color: #fff;
  box-shadow: 0 6px 24px #081e3233;
  transition: background 0.2s, transform 0.2s, box-shadow 0.2s;
}
.floating-whatsapp img {
  display: block;
  flex-shrink: 0;
  filter: brightness(0) invert(1);
}
.floating-whatsapp:hover {
  background: #0e6b38;
  transform: translateY(-2px);
  box-shadow: 0 8px 28px #081e324d;
}
.floating-whatsapp:focus-visible {
  outline: 3px solid #fff;
  outline-offset: 3px;
  box-shadow: 0 0 0 7px #081e32;
}
@media (max-width: 760px) {
  .floating-whatsapp {
    right: calc(16px + env(safe-area-inset-right, 0px));
    bottom: calc(16px + env(safe-area-inset-bottom, 0px));
  }
}
</style>
