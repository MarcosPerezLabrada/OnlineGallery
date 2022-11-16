<template>
  <div class="UploaderDiv">


  <input type="file" id="image-input" accept="image/jpeg, image/png, image/jpg">

  <div id="display-image"></div>

  <button onclick="Upload()" id="upload">Upload.</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {

  },
  methods:{
    Upload(){
      const upload = document.getElementById('upload');
      upload.addEventListener('click', function (e) {
        const link = document.createElement('a');
        link.upload = 'download.png';
        link.href = canvas.toDataURL();
        link.click();
        link.delete;
      });
    }
  }

  ,
  mounted(){
    const image_input = document.querySelector("#image-input");
    image_input.addEventListener("change", function() {
    const reader = new FileReader();
    reader.addEventListener("load", () => {
    const uploaded_image = reader.result;
    document.querySelector("#display-image").style.backgroundImage = `url(${uploaded_image})`;
  });
  reader.readAsDataURL(this.files[0]);
});



  }
}
</script>


<style scoped>
.UploaderDiv{
    text-align: center;
}
#display-image{
  width: 400px;
  height: 225px;
  border: 1px solid black;
  background-position: center;
  background-size: cover;
  text-align: center;
}
</style>
