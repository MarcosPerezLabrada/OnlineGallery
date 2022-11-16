<template>
  <div class="upload">
    <h1>Upload Something.</h1>
    <Uploader/>
  </div>
</template>

<script>
import Uploader from '@/components/Uploader.vue'
export default {
  name: 'UploadView',
  components: {
    Uploader,
  }
}
</script>
