<template>
  <social-sharing
    :url="constructedUrl"
    :title="this.$store.state.title"
    :description="this.$store.state.subtitle"
    hashtags="TamilBot,Blog"
    twitter-user="vuejs"
    inline-template
  >
    <div>
      <network network="facebook">
        <font-awesome-icon
          :icon="['fab', 'facebook']"
          style="font-size: 30px"
        />
      </network>
      <!-- <network network="twitter">
        <font-awesome-icon :icon="['fab', 'twitter']" style="font-size: 30px" />
      </network>
      <network network="pinterest">
        <font-awesome-icon
          :icon="['fab', 'pinterest']"
          style="font-size: 30px"
        />
      </network> -->
      <network network="whatsapp">
        <font-awesome-icon
          :icon="['fab', 'whatsapp']"
          style="font-size: 30px"
        />
      </network>
      <hr />
    </div>
  </social-sharing>
</template>
<script>
export default {
  name: 'MySocialSharing',
  data() {
    return {
      constructedUrl: 'blog.tamilbot.com' + `${this.$route.fullPath}`
    }
  }
}
</script>
