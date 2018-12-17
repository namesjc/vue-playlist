<template>
    <header>
        <h1 @click="changeTitle">{{ message }}-{{ title }}</h1>
    </header>
</template>

<script>
export default {
  name: 'app-header',
  props: {
      title: {
          type: String
      }
  },
  data () {
    return {
      message: "Vue.js Demo"
    }
  },
  methods: {
      changeTitle() {
        //   this.title = "changed";
        this.$emit("titleChanged", "child passes value to parent");
      }
  },
  beforeCreate() {
      alert("executed function before vue instance initialized");
  },
  created() {
      alert("vue instance initialize completed, but the page doesn't show");
  },
  beforeMount() {
      alert("before vue instance mounted, the page still doesn't show, but vDOM already configured");
  },
  mounted() {
      alert("vue instance mounted, the page shows after the method be executed")
  },
  beforeUpdate() {
      alert("before vue instance update, the page still not update, but vDOM already configured")
  },
  updated() {
      alert("vue instance update, the updated page show after the method be executed")
  },
  beforeDestroy() {
      alert("before vue instance destory")
  },
  destroyed() {
      alert("vue instance be destoryed")
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    header {
        background: lightgreen;
        padding: 10px;
    }

    h1 {
       color: #222;
       text-align: center; 
    }
</style>
