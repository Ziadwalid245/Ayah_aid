<template>
  <select v-model="selectedVerses" @change="sendSelectedVerses">
    <option disabled selected hidden value="">Pick Verses</option>
    <option value="3">3</option>
    <option value="5">5</option>
    <option value="10">10</option>
    <option value="15">15</option>
    <option value="20">20</option>
    <option value="25">25</option>
  </select>
</template>

<script lang="ts">
export default {
  name:"PickVerses",
  data() {
    return {
    selectedVerses:null as number | null 
    }
  },
  methods: {
    sendSelectedVerses(){
      this.$emit('send-selected-verses', this.selectedVerses)
    } 
  },
}
</script>
