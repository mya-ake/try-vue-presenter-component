<template>
  <ul>
    <PostListItemPresenter v-for="item in items" :key="item.id" v-bind="item">
      <PostListItem
        slot-scope="{ title, likeCount, handleClick }"
        :title="title"
        :likeCount="likeCount"
        @click="handleClick"
      />
    </PostListItemPresenter>
  </ul>
</template>

<script>
import PostListItemPresenter from "./PostListItemPresenter";
import PostListItem from "./PostListItem";

export default {
  components: {
    PostListItemPresenter,
    PostListItem
  },

  props: {
    items: {
      type: Array,
      required: true
    }
  }
};
</script>

<style lang="scss" scoped></style>
