<script setup lang="ts">
import Navbar from "./components/Navbar.vue"
import SiteDescr from "./components/SiteDescr.vue"
import GenerateTopic from "./components/GenerateTopic.vue"
import SendButton from "./components/SendButton.vue"
</script>
<template>
  <header>
    <Navbar />
  </header>
  <hero>
    <SiteDescr />
  </hero>
  <hr>
  <main>
    <GenerateTopic />
    <SendButton />
  </main>
</template>
<style>

header{
  padding: 0pz;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  background: hsla(139, 23%, 47%, 0.8);
  height: 50px;
}
hr{
  margin: 25px 0px 45px 0px;
  width: 60vw;
  margin-left: 70px;
  border: 1px solid ;
}
main{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  gap: 1rem;
}

</style>


