<template>
  <div class="page">
    <page-banner></page-banner>
    <page-content></page-content>
  </div>
</template>

<script>
import PageBanner from './page/Banner'
import PageContent from './page/Content'

export default {
  name: 'page',
  components: {
    PageBanner,
    PageContent
  }
}
</script>
