<template>
<section class="saved-lotto-numbers">
    <div class="saved-lotto-number-box" v-if="savedNumbers.length">
        <ul class="saved-number-list">
            <li v-for=" (savedlottoNumber,index) in savedNumbers" class="saved-lotto-number">

                <span class="eachnumber">{{savedlottoNumber.numbers}}</span>
                <!-- <span class="eachnumber" >{{ displayNumbers(savedlottoNumber.numbers)}}</span> -->

            </li>
        </ul>
    </div>
</section>
</template>
<script>
export default {
    name: "",
    props: ['savedNumbers'],
    data: function data() {
        return {

        }
    },
    computed: {
        displayNumbers: function(Numbers) {
            return Numbers;
        }
    },

    updated: function updated() {
        //do something after updating vue instance
        console.log(this.savedNumbers);
    }
}
</script>
<style lang="sass">.saved-lotto-numbers</style>
