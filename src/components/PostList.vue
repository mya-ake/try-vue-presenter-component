<template>
  <ul>
    <PostListItem
      v-for="(item, index) in items"
      v-bind="item"
      :key="item.id"
      :index="index"
      :handleClick="handleClick"
    />
  </ul>
</template>

<script>
import PostListItem from "./PostListItem";

export default {
  components: {
    PostListItem
  },

  props: {
    items: {
      type: Array,
      required: true
    },
    handleClick: {
      type: Function,
      required: true
    }
  }
};
</script>

<style lang="scss" scoped></style>
