<template>
  <div class="home">
    <PostListPresenter :items="items">
      <PostList
        slot-scope="{ items, handleClick }"
        :items="items"
        :handleClick="handleClick"
      />
    </PostListPresenter>
  </div>
</template>

<script>
import PostListPresenter from "@/components/PostListPresenter";
import PostList from "@/components/PostList";

export default {
  components: {
    PostListPresenter,
    PostList
  },

  computed: {
    items() {
      return [
        {
          id: 0,
          title: "test1",
          likeCount: 0
        },
        {
          id: 1,
          title: "test2",
          likeCount: 0
        },
        {
          id: 2,
          title: "test3",
          likeCount: 0
        }
      ];
    }
  }
};
</script>
