<template>
  <ShareButtonTemplate :url="url" :text="text">
    <span v-if="!fillColor" slot="shareIcon" class="has-text-white has-background-facebook button full-width is-hidden-print">
      <span class="icon mr-xs facebook" /><span>{{ buttonText }} </span>
    </span>
  </ShareButtonTemplate>
</template>

<script>
import ShareButtonTemplate from './ShareButtonTemplate'
export default {
  components: {
    ShareButtonTemplate
  },
  props: {
    /**
     * link to share
     */
    url: {
      type: String,
      default: null
    },
    /**
     * text for shared item
     */
    text: {
      type: String,
      default: ''
    },
    /**
     * text to include on the share button
     */
    buttonText: {
      type: String,
      default: 'Share'
    }
  }
}
</script>
<style lang="scss" scoped>
  .fb-share {
    width: 500px;
    height: 200px;
    background-color: red;
    color: yellow;
  }
</style>
