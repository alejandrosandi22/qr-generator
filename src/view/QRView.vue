<template>
  <div>
    <section>
      <span>
        <h1>QR Generator</h1>
        <h2>by Alejandro Sandí</h2>
      </span>
      <Form @inputValue="setValue" />
      <QR :value="value" />
    </section>
  </div>
</template>

<script>
import Form from "../components/Form.vue";
import QR from "../components/QR.vue";
export default {
  name: "QRView",
  data() {
    return {
      value: "https://alejandrosandi.com",
    };
  },
  components: {
    Form,
    QR,
  },
  methods: {
    setValue(inputValue) {
      this.value = inputValue;
    },
  },
};
</script>

<style scoped lang="scss">
div {
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: var(--background);
  section {
    width: 350px;
    height: 600px;
    background: var(--background);
    box-shadow: 5px 5px 10px #040507, -5px -5px 10px #10131b;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
    border-radius: 15px;
    padding: 20px;
    span {
      display: flex;
      flex-direction: column;
      justify-content: center;
      gap: 5px;
      h1 {
        color: #fff;
        font-size: 2rem;
        font-weight: normal;
      }
      h2 {
        color: var(--secondary-font-color);
        font-size: 1rem;
        margin: 0 0 0 10px;
        font-weight: lighter;
      }
    }
  }
}

@media (max-width: 768px) {
  div {
    section {
      width: 100%;
      height: 100%;
      min-height: 650px;
    }
  }
}
</style>
