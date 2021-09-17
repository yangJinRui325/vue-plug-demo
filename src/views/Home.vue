<template>
    <div class="home">
        测试下预览文件
        <iframe :src="pSrc"
                width="100%"
                height="100%">
        </iframe>
    </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  data(){
      return {
          pSrc: ""
      }
  },
  mounted(){
    this.loadPDF()
  },
  components: {
  },
  methods:{
    loadPDF () {
        //baseurl ：pdf存放的文件路径，可以是本地的，也可以是远程，这个是远程的，亲测可以用
        let baseurl = 'http://localhost:8080/pdfdemo.pdf';
        //ie有缓存加个随机数解决 + '?r=' + new Date()
        let pSrc = baseurl + '?r=' + new Date();
        this.pSrc = '../../pdf/web/viewer.html?file=' + encodeURIComponent(pSrc) + '.pdf';
    }
  }
}
</script>
<style scoped>
.home {
    position: relative;
    width: 100%;
    height: 100%;
}
</style>
