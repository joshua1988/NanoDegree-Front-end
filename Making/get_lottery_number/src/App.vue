<template>
  <div id="app">
    <lottoHeader></lottoHeader>
    <lottoNumberSetting v-on:makeLottoNumber="makeLottoNumber" v-on:saveLottoNumber="saveLottoNumber"></lottoNumberSetting>
    <lottoNumberList :giveLottoNumber="lottoNumbers"></lottoNumberList>
    <lottoNumberSaveList :savedNumbers="savedNumbers" v-on:deleteLottoNumbers="deleteLottoNumbers"
     v-on:allCLear="allCLear" :savedNumbersCount="savedNumbersCount"
    ></lottoNumberSaveList>
    <gotoBuyLotto></gotoBuyLotto>
    <lottoFooter></lottoFooter>
  </div>
</template>

<script>
import lottoHeader from './components/lottoHeader.vue'
import lottoNumberSetting from './components/lottoNumberSetting.vue'
import lottoNumberList from './components/lottoNumberList.vue'
import lottoNumberSaveList from './components/lottoNumberSaveList.vue'
import lottoFooter from './components/lottoFooter.vue'
import gotoBuyLotto from './components/goToBuyLotto.vue'

export default {
  name: 'app',

  data () {
    return {
      lottoNumbers:[],
      savedNumbers:[],
      index:0,
      savedNumbersCount: localStorage.length

    }
  },
  components: {
    lottoHeader: lottoHeader,
    lottoNumberSetting: lottoNumberSetting,
    lottoNumberList: lottoNumberList,
    lottoNumberSaveList: lottoNumberSaveList,
    lottoFooter: lottoFooter,
    gotoBuyLotto: gotoBuyLotto
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
      // 버튼이 눌리면 savebutton이 나오기 때문에
      // validation 필요가 없음
        // var STORAGE_KEY = 'Get Lotto Number version.1'
        this.index++;
        var lotto_number = this.lottoNumbers;
        var templottoNumbers ={}
        templottoNumbers.numbers = lotto_number;
        templottoNumbers.index = this.index;

        this.savedNumbers.push(templottoNumbers);
        localStorage.setItem(this.index, JSON.stringify(templottoNumbers))
        this.savedNumbersCount = localStorage.length;
        //로컬스토리지 덮어 쓴다.


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
    deleteLottoNumbers(savedlottoNumber,localIndex,appdataIndex){
      console.log('하이:',savedlottoNumber,localIndex,appdataIndex);
      console.log(this.savedNumbers);
      localStorage.removeItem(localIndex);
      this.savedNumbers.splice(appdataIndex, 1);

      // 3번째 인덱스를 삭제했을 때 index값은 2가 나옴
      //
      this.savedNumbersCount = localStorage.length;
    },
    allCLear(){
      this.savedNumbers =[];
      localStorage.clear();
      this.index = 0;
    },
  },
    watch: {
     savedNumbers: {
     handler: function (lottoNumber) {
         console.log("changed");
       }
    },
    savedNumbersCount:{
      handler: function(lottoNumber){
        console.log("갯수를 세줘 ");
      }
    }
   }
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
