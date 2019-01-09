<template>
  <li>
    <div>{{ title }}</div>
    <button type="button" @click="handleClick(index)">
      link: {{ likeCount }}
    </button>
  </li>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },

    handleClick: {
      type: Function,
      required: true
    },

    likeCount: {
      type: Number,
      required: true
    },

    index: {
      type: Number,
      required: true
    }
  }
};
</script>

<style lang="scss" scoped></style>
