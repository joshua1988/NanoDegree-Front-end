<template>
  <section class="saved-lotto-numbers">
    <div class="saved-lotto-number-box">
      <ul  class="saved-number-list">
      <li v-for=" (savedlottoNumber,key) in savedNumbers" class="lotto-number">{{savedlottoNumber}}</li>
      </ul>
    </div>
  </section>
</template>
<script>
export default {
  name: "",
  props:['savedNumbers'],
  data: function data() {
    return {

    }
  }
}
</script>
<style>
</style>
