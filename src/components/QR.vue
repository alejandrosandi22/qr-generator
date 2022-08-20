<template>
  <div class="qr-wrapper">
    <QRcodeVue :value="value" :size="240" level="H" background="#fff" />
  </div>
  <button @click="download">
    <p>Download</p>
    <i class="fal fa-download"></i>
  </button>
</template>

<script>
import QRcodeVue from "qrcode.vue";
export default {
  name: "QR",
  props: ["value"],
  components: {
    QRcodeVue,
  },
  methods: {
    downloadQR() {
      const canvas = document.querySelector(".qr-wrapper canvas");
      const link = document.createElement("a");
      link.href = canvas.toDataURL("image/png");
      link.download = "qr.png";
      link.click();
    },
  },
};
</script>

<style scoped lang="scss">
.qr-wrapper {
  background: var(--white);
  border: 1px solid #000;
  border-radius: 15px;
  width: 280px;
  height: 280px;
  display: grid;
  place-items: center;
}
button {
  display: flex;
  border: none;
  outline: none;
  background: none;
  cursor: pointer;
  p {
    font-size: 1rem;
    font-weight: normal;
    color: var(--primary-font-color);
  }
  i {
    margin: 0 0 0 10px;
    font-size: 1rem;
    color: var(--primary-font-color);
  }
  &:hover {
    i,
    p {
      color: var(--secondary-font-color);
    }
  }
}
</style>
