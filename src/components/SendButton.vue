<template>
  <PickVerses @send-selected-verses="getVerses" />
  <PickSurah @send-surah-number="getSurahNumber" />
  <PickTime @send-time="getTime" />
  <button @click="fetchSurah">Get Data</button>
  <button @click="logData">Log Data</button>
  <button @click="sendAyahs">Send</button>
</template>
<script lang="ts">
import PickVerses from './PickVerses.vue';
import PickSurah from './PickSurah.vue';
interface Ayahs{
  number:number,
  text:string
}
export default {
  name:"SendButton",
  components:{
    PickSurah,
    PickVerses
  },
  data() {
    return {
      surahNumber:null as number | null,
      time:[] as number[],
      verses: 0,
      ayahs:"" 
    }
  },
  methods: {
    sendAyahs(){
    this.sendData();
    },
    getSurahNumber(data:number){
      this.surahNumber = data;
    },
    getTime(data:[]){
    this.time = data;
    },
    getVerses(data:number){
      this.verses = data;
    },
    fetchSurah(){
      fetch(`http://api.alquran.cloud/v1/surah/${this.surahNumber}?limit=${this.verses}`)
        .then(res => res.json())
        .then(data => {
          const surahData: Ayahs[] = data.data.ayahs;
          for (let i = 0; i < surahData.length; i++){
            const ayahsText = surahData[i].text;
            this.ayahs += ayahsText;
          }
        })
    },
    logData(){
      console.log(this.ayahs);
    },
    sendData(){
    fetch('https://ntfy.sh/2561576913133837158', {
        method: 'POST', // PUT works too
        body:this.ayahs
})
    },
}
}
</script>
