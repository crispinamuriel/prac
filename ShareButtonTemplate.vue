<template>
  <span class="acluvl">
    <a :href="shareUrl" class="no-underline hp__acluvl_facebook_share" alt="Post this to facebook" target="_blank">
      <slot name="shareIcon" />
    </a>
  </span>
</template>
<script>
export default {
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
    }
  },
  computed: {
    shareUrl() {
      // This is the more "correct" way to share a link but assumes we have a fb app id:
      // return `https://www.facebook.com/dialog/share?app_id=${this.facebookAppId}&display=popup&href=${encodeURIComponent(this.shareUrl)}&redirect_uri=${encodeURIComponent(this.shareUrl)}`;

      // The old way still works:
      let params = []
      if (this.url) params.push(`u=${encodeURIComponent(this.url)}`)
      if (this.text) params.push(`quote=${encodeURIComponent(this.text)}`) // quote is the only param for text that seems to work anymore
      return `https://www.facebook.com/sharer/sharer.php?${params.join('&')}`
    }
  }
}
</script>

