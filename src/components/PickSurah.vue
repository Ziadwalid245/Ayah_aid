<template>
  <select  v-model="selectedSurahNumber" id="pick-surah" @change="sendSurahNumber">
    <option disabled selected hidden value=""> Pick a Surah</option>
    <option  v-for="surah in surahs" :value="surah.number" :key="surah.number">
      {{surah.name}}
    </option>
  </select>
</template>

<script lang="ts">

interface Surah{
  number:number,
  name:String,
  englishName:String
}
export default {
  name:"PickSurah",
  data() {
    return {
      selectedSurahNumber: null as number | null,
      surahs:[] as Surah[]
    }
  },
  mounted() {
    this.getSurahs();
  },
  methods: {
    getSurahs(){
      fetch("https://api.alquran.cloud/v1/surah")
        .then(res => res.json())
        .then(data => {
          const surahData = data.data;
          this.surahs = surahData;
        });
    },
    sendSurahNumber(){
      this.$emit('send-surah-number', this.selectedSurahNumber)
    }
  },
}
</script>


