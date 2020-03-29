<template>
  <div id="home-page" class="page-wrapper home-page">
    <site-hero
      title="அறிவோம் தெளிவோம்!"
      :subtitle="subtitle"
      :image="featureImage"
    >
      <button class="button is-primary" @click="goToSite()">
        Visit TamilBot
      </button>
    </site-hero>
    <main-section theme="one-column">
      <template v-slot:default>
        <!-- All Posts -->
        <posts-grid />
      </template>
    </main-section>
    <my-social-sharing />
  </div>
</template>

<script>
import { mapState } from 'vuex'
import { setPageData } from '../helper'

export default {
  name: 'HomePage',
  head() {
    return {
      title: `Home | ${this.$siteConfig.siteName}`
    }
  },
  computed: {
    ...mapState(['title', 'subtitle', 'featureImage'])
  },
  fetch({ store, params }) {
    setPageData(store, { slug: 'home' })
  },
  methods: {
    goToSite() {
      window.open(
        'https://www.tamilbot.com',
        '_blank' // <- This is what makes it open in a new window.
      )
    }
  }
}
</script>

<style>
.home-page .under-subtitle {
  border-top: none;
}
</style>
