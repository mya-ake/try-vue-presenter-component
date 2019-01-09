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
    items: {
      type: Array,
      required: true
    }
  },

  data() {
    return {
      displayItems: this.items.map(this.buildItem)
    };
  },

  methods: {
    buildItem(item) {
      return {
        ...item
      };
    },

    countUp(index) {
      const item = this.displayItems[index];
      item.likeCount++;
      this.$set(this.displayItems, index, this.buildItem(item));
    }
  },

  render(h) {
    const slot = this.$scopedSlots.default;
    if (typeof slot !== "function") {
      return createRenderless(h, this.$slots.default);
    }
    const nodes = slot({ items: this.displayItems, handleClick: this.countUp });
    return createRenderless(h, nodes);
  }
};
</script>

<style lang="scss" scoped></style>
