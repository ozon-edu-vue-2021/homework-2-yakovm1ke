<template>
  <div class="link-wrapper">
    <div
      :class="linkClasses"
      @click="clickHandler"
    >
      <img src="../../assets/icons/link.svg" alt="folder">
      {{ name }}
    </div>
  </div>
</template>

<script>
export default {
  name: "LinkItem",
  props: {
    name: {
      type: String,
      required: true,
    },
    type: {
      type: String,
      required: true,
    },
    target: {
      type: String,
      default: '',
    },
  },
  data: () => ({
    selected: false,
  }),
  methods: {
    clickHandler() {
      this.selected = !this.selected;
    }
  },
  computed: {
    linkClasses() {
      return ['link-item', {
        'link-item_selected': this.selected,
      }]
    }
  },
}
</script>

<style scoped>
.link-wrapper {
  width: 100%;
}

.link-item {
  display: inline-flex;
  text-decoration: underline;
  height: 20px;
  align-items: center;
  padding: 3px 5px;
  border-radius: 4px;
}

.link-item_selected {
  color: #FFFFFF;
  background-color: #8D95A5;
}

.link-item:hover {
  cursor: pointer;
  color: #216BFF;
  background-color: #D6D9DC;
}

.link-item img {
  display: flex;
  justify-content: center;
  width: 12px;
  height: 12px;
  margin-right: 10px;
}
</style>