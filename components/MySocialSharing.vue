<template>
  <social-sharing
    :url="this.url"
    :title="this.title"
    :description="this.description"
    hashtags="TamilBot,Blog"
    twitter-user="vuejs"
    inline-template
  >
    <div>
      <network network="facebook">
        <font-awesome-icon :icon="['fab', 'facebook']" />
      </network>
      <network network="twitter">
        <font-awesome-icon :icon="['fab', 'twitter']" />
      </network>
      <network network="pinterest">
        <font-awesome-icon :icon="['fab', 'pinterest']" />
      </network>
      <network network="whatsapp">
        <font-awesome-icon :icon="['fab', 'whatsapp']" />
      </network>
    </div>
  </social-sharing>
</template>
<script>
export default {
  name: 'MySocialSharing'
}
</script>
