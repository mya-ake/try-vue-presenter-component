<template>
  <li>
    <div>{{ title }}</div>
    <button type="button" @click="handleClick">link: {{ likeCount }}</button>
  </li>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },

    likeCount: {
      type: Number,
      required: true
    }
  },

  methods: {
    handleClick() {
      this.$emit("click");
    }
  }
};
</script>

<style lang="scss" scoped></style>
