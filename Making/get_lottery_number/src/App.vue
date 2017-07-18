<template>
  <div id="app">
    <lottoHeader></lottoHeader>
    <lottoNumberSetting v-on:makeLottoNumber="makeLottoNumber" v-on:saveLottoNumber="saveLottoNumber"></lottoNumberSetting>
    <lottoNumberList :giveLottoNumber="lottoNumbers"></lottoNumberList>
    <lottoNumberSaveList :savedNumbers="savedNumbers" v-on:deleteLottoNumbers="deleteLottoNumbers"></lottoNumberSaveList>
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
        var templottoNumbers ={}
        templottoNumbers.numbers = this.lottoNumbers

        this.savedNumbers.push(templottoNumbers)
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
  // watch: {
  //   lottoNumbers: {
  //     handler: function (lottoNumber) {
  //       console.log("changed");
  //     }
  //   }
  // },
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
