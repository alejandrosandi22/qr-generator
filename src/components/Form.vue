<!-- eslint-disable vue/no-mutating-props -->
<template>
  <form @submit="submit">
    <input v-model="value" type="text" placeholder="Enter your text or URL" />
    <button>
      <i class="fas fa-paper-plane"></i>
    </button>
  </form>
</template>

<script>
export default {
  name: "Form",
  data() {
    return {
      value: "",
    };
  },
  methods: {
    submit(e) {
      e.preventDefault();
      this.$emit("inputValue", this.value);
    },
  },
};
</script>

<style scoped lang="scss">
form {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  input {
    width: 100%;
    height: 45px;
    border: 1px solid var(--white);
    border-right: none;
    border-radius: 10px 0 0 10px;
    padding: 0 20px;
    font-size: 1rem;
    font-weight: normal;
    color: #fff;
    background: var(--background);
    outline: none;
  }
  button {
    height: 45px;
    border: 1px solid var(--white);
    border-radius: 0 10px 10px 0;
    padding: 0 15px;
    font-size: 18px;
    font-weight: normal;
    color: var(--background);
    background: var(--primary-font-color);
    outline: none;
    &:hover {
      background: var(--secondary-font-color);
    }
  }
}
</style>
