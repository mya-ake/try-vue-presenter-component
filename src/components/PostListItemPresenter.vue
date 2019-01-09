<script>
const createRenderless = (h, vnode) => {
  if (!Array.isArray(vnode)) {
    return vnode;
  }
  if (vnode.length === 1) {
    return vnode[0];
  }
  return vnode;
};

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

  data() {
    return {
      item: this.buildItem()
    };
  },

  methods: {
    buildItem() {
      return {
        // 表示用のプロパティの追加とか
        ...this.$props
      };
    },

    countUp() {
      // API のリクエストとか
      this.item.likeCount++;
    }
  },

  render(h) {
    const slot = this.$scopedSlots.default;
    if (typeof slot !== "function") {
      return createRenderless(h, this.$slots.default);
    }
    const nodes = slot({ item: this.item, handleClick: this.countUp });
    return createRenderless(h, nodes);
  }
};
</script>

<style lang="scss" scoped></style>
