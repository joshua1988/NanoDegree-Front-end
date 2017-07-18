<template>
  <div id="app">
    <lottoHeader></lottoHeader>
    <lottoNumberSetting v-on:makeLottoNumber="makeLottoNumber" v-on:saveLottoNumber="saveLottoNumber"></lottoNumberSetting>
    <lottoNumberList :giveLottoNumber="lottoNumbers"></lottoNumberList>
    <lottoNumberSaveList :savedNumbers="savedNumbers" @v-on:deleteLottoNumbers="deleteLottoNumbers"></lottoNumberSaveList>
    <lottoFooter></lottoFooter>
  </div>
</template>

<script>
import lottoHeader from './components/lottoHeader.vue'
import lottoNumberSetting from './components/lottoNumberSetting.vue'
import lottoNumberList from './components/lottoNumberList.vue'
import lottoNumberSaveList from './components/lottoNumberSaveList.vue'
import lottoFooter from './components/lottoFooter.vue'
export default {
  name: 'app',

  data () {
    return {
      lottoNumbers:[],
      savedNumbers:[]

    }
  },
  components: {
    lottoHeader: lottoHeader,
    lottoNumberSetting: lottoNumberSetting,
    lottoNumberList: lottoNumberList,
    lottoNumberSaveList: lottoNumberSaveList,
    lottoFooter: lottoFooter
  },
  methods: {
    makeLottoNumber() {
      const MaxNumber = 45;
      var numberList=[];
      for(var i=0; i<MaxNumber; i++){
        numberList.push(i+1);
      }
      var lottolength = MaxNumber;

      // shuffle
      numberList =  this.shuffle(numberList,lottolength);
      // get 6 Numbers
      this.lottoNumbers = numberList.slice(0,6);
      console.log(this.lottoNumbers);
  	},
    saveLottoNumber(){
      var value = this.lottoNumbers.length
      if(value){
        //savedNumber의 속성값을 늘려줘야 되는데 음 ...
        // this.savedNumbers.first
        var templottoNumbers = {};

        // #1 - this.lottoNumbers 는 아래에서 찍히는 것처럼 타입이 object 입니다.
        // console.log(typeof this.lottoNumbers);

        // #2 - templottoNumbers 의 빈 객체 선언후 왜 numbers 에 넣으셨나요?
        //      값을 복사하는 거라면 반복문을 활용하시거나 아래 #3 처럼 값을 통째로 복사하는 방법도 있지만,
        //      추후에 상태관리나 Reactivity system 관점에서 봤을 때 데이터 참조 값을 그대로 복사하면
        //      아마 다른 부작용이 있을겁니다. 구현해보시면서 이로 인해 생기는 문제점이 있으면 공유해주세요!
        // templottoNumbers.numbers = this.lottoNumbers;

        this.savedNumbers = this.lottoNumbers;
        // this.savedNumbers.push(templottoNumbers);
      }
      else{
        alert('저장할 번호가 없어요 !!!')
      }
    },
    shuffle(items,n){
      while (n--) {
        var i = Math.floor(n * Math.random());
        var tmp = items[i];
        items[i] = items[n];
        items[n] = tmp;
      }
      return items;
      // https://jsperf.com/array-shuffle-comparator/5
    },
    deleteLottoNumbers(item,index){
      console.log('하이');
      console.log(this.savedNumbers);
      this.savedNumbers.splice(index, 1);
    }
  },
  watch: {
    // savedNumbers: {
    //   handler: function (lottoNumber) {
    //     console.log("changed");
    //   }
    // }
  },
}


</script>

<style lang="sass">
*
  box-sizing: border-box
html
  font-family: 'Roboto', sans-serif
  font-size: 16px
body
  min-height: 100vh
  background-color: #f59735
  position: relative
ul
  padding: 0
li
  list-style: none

body,h1,ul
  margin: 0

</style>
