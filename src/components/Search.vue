<script>

export default {
  data() {
    return {
      term: "",
    };
  },

  emits: ["on-search"],

  methods: {
    clear() {
      this.term = "";
      this.$emit("on-search", this.term);
    },

    search() {
      this.$emit("on-search", this.term);
    },
  },
};
</script>

<template>
  <form @submit.prevent="">
    <div class="input-group">
      <input
        type="text"
        class="form-control"
        placeholder = "Cerca..."
        v-model="term"
        @keyup.enter="search"
      />
      <button class="btn btn-success" type="button" @click="search">
        Search
      </button>
      <button class="btn btn-warning" type="button" @click="clear">
        Reset
      </button>
    </div>
  </form>
</template>

<style lang="scss" scoped></style>