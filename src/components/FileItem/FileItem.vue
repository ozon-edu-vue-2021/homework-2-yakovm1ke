<template>
  <div class="file-wrapper">
    <div
      :class="fileClasses"
      @click="clickHandler"
    >
      <img src="../../assets/icons/file.svg" alt="folder">
      {{ name }}
    </div>
  </div>
</template>

<script>
export default {
  name: "FileItem",
  props: {
    name: {
      type: String,
      required: true,
    },
    type: {
      type: String,
      required: true,
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
    fileClasses() {
      return ['file-item', {
        'file-item_selected': this.selected,
      }]
    }
  },
}
</script>

<style scoped>
.file-wrapper {
  width: 100%;
}

.file-item {
  display: inline-flex;
  align-items: center;
  height: 20px;
  padding: 3px 5px;
  border-radius: 4px;
}

.file-item_selected {
  color: #FFFFFF;
  background-color: #8D95A5;
}

.file-item:hover {
  cursor: pointer;
  color: #216BFF;
  background-color: #D6D9DC;
}

.file-item img {
  display: flex;
  justify-content: center;
  width: 12px;
  height: 12px;
  margin-right: 10px;
}
</style>