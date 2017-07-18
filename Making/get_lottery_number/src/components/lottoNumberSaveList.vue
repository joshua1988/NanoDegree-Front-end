<template>
<section class="saved-lotto-numbers">
    <div class="saved-lotto-number-box" v-if="savedNumbers.length">
        <ul class="saved-number-list">
            <li v-for=" (savedlottoNumber,index) in savedNumbers" class="saved-lotto-number">

                <span class="each-number">{{savedlottoNumber}}</span>
                <span class="btn-save-lottonumber-icon" @click="deleteLottoNumbers(savedlottoNumber,index)">
                  <i class="fa fa-trash-o" aria-hidden="true"></i>
                </span>
                <!--method로 바꾸려는 시도   -->
                <!-- <span class="each-number">{{displayNumbers(savedlottoNumber.numbers)}}</span> -->

                <!-- #3 -->
                <!-- methods 로 바꾸시려면 v-on:click 이나 @click 으로 사용하시면 되지 않을까요? -->
                <!-- 왜 v-text 를 사용하셨는지는 모르겠지만, v-text 역할이 {{ }} 와 동일하므로 가급적 {{ }} 사용하시길  -->
                <span class="each-number-for-method" v-on:click="displayNumbers(savedlottoNumber)">{{savedlottoNumber}}</span>

                <!--Computed 적용하려 했으나 잘 안 됨   -->
                <!-- <span class="eachnumber" >{{ displayNumbers(savedlottoNumber.numbers)}}</span> -->
                <!-- <span class="each-number" v-text="displayNumbers(savedlottoNumber.numbers)"></span> -->

                <!-- #4 -->
                <!-- 희찬님이 computed 로 어떤걸 구현하려는 건지는 모르겠으나, 일단 computed 와 methods 의 가장 큰 차이점은
                1. computed 계산된 값이 캐시가 된다는 점.
                2. computed 인자를 받을 수 없다는 점
                3. 인자를 받기 위해서는 methods 를 사용한다는 점
                을 먼저 정확히 구분하셔야 합니다. https://vuejs.org/v2/guide/computed.html#Computed-Caching-vs-Methods 참고

                그럼에도 불구하고 computed 를 편법으로 사용하시고 싶으면,
                아래 computed 에 구현한 map() 방식을 참고하세요. -->
                <span class="eachnumber">{{ doubleSavedLottoNumber }}</span>

            </li>
        </ul>
    </div>
    <button type="button" @click="showNumbers">show</button>
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
        doubleSavedLottoNumber() {
          return this.savedNumbers.map(function (data) {
            data *= 2;
            return data;
          });
        }
    },
    methods: {
      showNumbers() {
        console.log(this.savedNumbers);
      },
      deleteLottoNumbers(savedlottoNumber,index){
        this.$emit('deleteLottoNumbers',savedlottoNumber,index);
        console.log(savedlottoNumber,index);
      },
      displayNumbers(lottoNumber) {
        console.log("add logic here", lottoNumber);
      }
    },
    updated: function updated() {
        //do something after updating vue instance
        console.log(this.savedNumbers);
    }
}
</script>
<style lang="sass">
.saved-lotto-numbers
  width: 100%
  text-align: center
  background-color: #ffeaba
  line-height: 2.5em

.btn-make-lottonumber-icon,.btn-save-lottonumber-icon
  text-align: center
  display: inline-block
  width: 2em
  height: 2em
  border-radius: 0.3em
  line-height: 2em

.each-number-for-method
  border-style: solid

</style>
