<template>
  <div class="home"><PostList :items="items" /></div>
</template>

<script>
import PostList from "@/components/PostList";

export default {
  components: {
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
