<template>
  <div>
    <directory
      v-for="(dir, i) in dirs"
      :key="i + dir.name"
      :type="dir.type"
      :name="dir.name"
      :contents="dir.contents"
    />
    <file-item
      v-for="(file, i) in files"
      :key="i + file.name"
      :type="file.type"
      :name="file.name"
    />
    <link-item
      v-for="(link, i) in links"
      :key="i + link.name"
      :type="link.type"
      :name="link.name"
      :target="link.target"
    />
  </div>
</template>

<script>
export default {
  name: 'Contents',
  components: {
    Directory: () => import('@/components/Directory/Directory'),
    FileItem: () => import('@/components/FileItem/FileItem'),
    LinkItem: () => import('@/components/LinkItem/LinkItem'),
  },
  props: {
    contents: {
      type: Array,
      default: () => ([]),
    }
  },
  data: () => ({
    dirs: [],
    files: [],
    links: [],
  }),
  methods: {
    createItems() {
      this.contents.forEach(item => {
        switch (item.type) {
          case 'directory':
            this.dirs.push(item);
            break;
          case 'file':
            this.files.push(item);
            break;
          case 'link':
            this.links.push(item);
            break;
        }
      })
    }
  },
  created() {
    this.createItems();
  }
};

</script>

<style scoped>

</style>