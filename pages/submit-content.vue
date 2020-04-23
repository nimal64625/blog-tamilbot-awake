// Unsused - as this page is moved to CMS post
<template>
  <div id="about-page" class="page-wrapper about-page content-page">
    <site-hero
      title="Welcome Content Writers!!"
      subtitle="We are happy to accept and host your content!"
      image="/uploads/about-banner.jpeg"
    ></site-hero>
    <main-section theme="sidebar-right">
      <template v-slot:default>
        <div class="content">
          <p>
            <b>"Stories by Kids"</b> is a special category where we accept
            content from kids in the age range of 5 to 15. Kids name and age
            will be published as Author of the content in Blog site. We
            encourage parents to help with the process of submitting contents
            through either of the ways below:
          </p>
          <p>
            1. Submit through tamilbot.com (PREFERRED): Create an account and
            login to tamilbot.com, and submit the content for review; Please
            ensure to quote that you want to publish it in blog under the
            category "Stories By Kids"
          </p>
          <p>
            2. Submit through Email: Send the content as attachment or plain
            text to <i>editor@tamilbot.com </i>
          </p>
          <hr />
          <p>
            <b>"Fan Page"</b> is a category where we accept stories and content
            designed for kids. It'll be published under separate category with
            your preferred Name as Author. We encourage authors to submit the
            content through either of the ways below:
          </p>
          <p>
            1. Submit through tamilbot.com (PREFERRED): Create an account and
            login to tamilbot.com, and submit the content for review; Please
            ensure to quote that you want to publish it in blog under the
            category "Fan Page"
          </p>
          <p>
            2. Submit through Email: Send the content as attachment or plain
            text to <i>editor@tamilbot.com </i>
          </p>
          <hr />
          <p>
            Thanks for choosing our Blog. Looking forward to interact with you!
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
      title: `Submit Blog | ${this.$siteConfig.siteName}`
    }
  }
}
</script>
