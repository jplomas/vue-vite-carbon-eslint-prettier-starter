<template>
  <div class="sample">
    <h1>Example use of @carbon/vue</h1>
    <cv-text-input v-model="yourName" label="Who are you?" placeholder="your name" />
    <cv-button @click="onClick">Hello {{ yourName }}</cv-button>
    <cv-modal :visible="visible" @modal-hidden="modalClosed">
      <template #title>Welcome to @carbon/vue {{ yourName }}</template>
      <template #content>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, seed do eiusmod tempor incididunt ut labore et
          dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
          commodo consequat.
        </p>
      </template>
    </cv-modal>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      yourName: '',
      visible: false,
    };
  },
  methods: {
    onClick() {
      this.visible = true;
    },
    modalClosed() {
      this.visible = false;
    },
  },
};
</script>

<style>
.sample {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  max-width: 600px;
  margin: 5% auto;
}

.cv-text-input {
  margin: 30px 0;
}
</style>
