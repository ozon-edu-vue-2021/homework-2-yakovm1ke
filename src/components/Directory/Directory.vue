<template>
  <div class="directory">
    <div
      class="directory-name-wrapper"
    >
      <div
        class="directory-name"
        @click="clickHandler"
      >
        <img src="../../assets/icons/folder.svg" alt="folder">
        {{ name }}
      </div>
    </div>
    <contents
        v-show="showContents"
        class="contents"
        :contents="contents"/>
  </div>
</template>

<script>

export default {
  name: 'Directory',
  components: {
    Contents: () => import('../Contents/Contents.vue')
  },
  data: () => ({
    showContents: false,
  }),
  props: {
    contents: {
      type: Array,
      default: () => ([]),
    },
    name: {
      type: String,
      required: true,
    },
    type: {
      type: String,
      required: true,
    }
  },
  methods: {
    clickHandler() {
      this.showContents = !this.showContents;
    }
  }
};

</script>

<style scoped>
.directory {
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

.directory-name {
  font-weight: bold;
  display: inline-flex;
  align-items: center;
  height: 20px;
  padding: 3px 5px;
  border-radius: 4px;
}

.directory-name:hover {
  cursor: pointer;
  color: #216BFF;
  background-color: #D6D9DC;
}

.directory-name img {
  display: flex;
  justify-content: center;
  width: 12px;
  height: 12px;
  margin-right: 10px;
}

.directory .contents {
  padding-left: 20px;
}
</style>