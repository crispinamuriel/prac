<template>
  <ShareButtonTemplate></ShareButtonTemplate>
</template>
<script>
import ShareButtonTemplate from "./ShareButtonTemplate";
export default {
  components: {
    ShareButtonTemplate
  },
  data() {
    return {
      url: "www.google.com"
    }
  }
}
</script>
  <style>
  .fb-share {
    width: 500px;
    height: 200px;
    background-color: red;
    color: yellow;
  }
  </style>
