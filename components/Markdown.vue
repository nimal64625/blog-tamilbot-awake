<template>
  <v-runtime-template
    class="content text"
    :template="content"
  ></v-runtime-template>
</template>

<script>
import MarkdownIt from 'markdown-it'
import VRuntimeTemplate from 'v-runtime-template'

export default {
  name: 'Markdown',
  components: { VRuntimeTemplate },
  props: {
    tag: { type: String, default: 'article' },
    markdown: { type: String, required: true }
  },
  computed: {
    content() {
      const md = new MarkdownIt({
        linkify: true,
        typographer: true
      })
        .use(require('markdown-it-deflist'))
        .use(require('markdown-it-sub'))
        .use(require('markdown-it-sup'))
        .use(require('markdown-it-footnote'))
      let html = md.render(this.markdown)

      html = this.useResponsiveImages(html)
      html = this.wrapTable(html)
      html = html.replace(/<table>/g, '<table class="table is-striped">')

      return `<div class="content">${html}</div>`
    }
  },
  methods: {
    useResponsiveImages(html) {
      const images = html.match(/<img(.*?)>/g)
      if (images) {
        images.forEach((image) => {
          // const generatedImage = require('~/assets')
          const origImage = image
            .match(/src="([^"]*)"/g)[0]
            .replace('src="', '')
            .replace('"', '')
          let replace = `src="${origImage}"`
          if (origImage.startsWith('/')) {
            const generatedImage = require(`~/assets${origImage}`)
            replace = `src="${generatedImage.src}" srcset="${generatedImage.srcSet}"`
          }

          const optiImage = image
            .replace('<img', '<opti-image')
            .replace('>', '/>')
            .replace(/src="([^"]*)"/g, replace)
          html = html.replace(image, optiImage)
        })
      }
      return html
    },
    wrapTable(html) {
      html = html.replace(/<table/g, `<div class="table-wrapper"><table`)
      html = html.replace(/<\/table>/g, `</table></div>"`)
      return html
    }
  }
}
</script>

<style scoped>
@font-face {
  font-family: 'vanavil-avvaiyar';
  src: url('/fonts/vanavil Avvaiyar.TTF') format('truetype');
  font-weight: normal;
  font-style: normal;
}
@font-face {
  font-family: 'agni';
  src: url('/fonts/Agni.ttf') format('truetype');
  font-weight: normal;
  font-style: normal;
}
@font-face {
  font-family: 'kurinchi';
  src: url('/fonts/Kurinchi ACI1.ttf') format('truetype');
  font-weight: normal;
  font-style: normal;
}
.text {
  font-family: 'kurinchi';
  font-weight: 300;
  @media (min-width: 768px) {
    font-size: 3.2rem;
  }
}
</style>
