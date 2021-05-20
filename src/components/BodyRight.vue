<template>
    <div class="body-right">
        <HeaderRight />
        <ContentRight />
    </div>
</template>

<script>
import HeaderRight from './component-right/HeaderRight'
import ContentRight from './component-right/ContentRight'

export default {
  name: 'BodyRight',
  components: {
    HeaderRight,
    ContentRight
  }
}
</script>

