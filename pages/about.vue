<template>
  <div id="about-page" class="page-wrapper about-page content-page">
    <site-hero
      title="ABOUT"
      subtitle="Know Who We Are"
      image="/uploads/about-banner.jpeg"
    ></site-hero>
    <main-section theme="sidebar-right">
      <template v-slot:default>
        <div class="content">
          <p>
            Before you read further.. Why do you see English in some of the
            places in a Tamil Blog site? That's just need of the time where we
            have to keep certain portions of our site in English until search
            engine users become well versed with Tamil based search.
          </p>
          <p>
            Lets focus on what you should know about us - We are set of Tamil
            enthusiasts working together to serve Tamil content in the best
            possible way. Our articles are kept simple and made to the point
            what is intended to convey. Our primary focus is to take Tamil
            language to the maximum possible audience via technology.
          </p>
          <p>
            We offer services (via
            <a href="https://www.tamilbot.com">www.tamilbot.com</a>) to
            students, authors, business organizations to review their creations
            and thoughts and to make them publish ready.
          </p>
          <p>
            Enjoy our blog and services. If you dont like anything, let us know;
            If you like something, let everyone know..
          </p>
          <p>
            Contact Us:
            <a href="mailto:support@tamilbot.com">support@tamilbot.com</a>
          </p>
        </div>
      </template>

      <template v-slot:sidebar>
        <h3 class="subtitle is-4">
          Latest Posts
        </h3>
        <posts-grid :per-row="1" :number="2" />
      </template>
    </main-section>
  </div>
</template>
<script>
export default {
  head() {
    return {
      title: `About | ${this.$siteConfig.siteName}`
    }
  }
}
</script>
