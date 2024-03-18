<template>
  <h1 class="site-header">AYAH AID</h1>
  <div class="description-container">
    <p> AYAH AID is a tool that allows you to pick a surah, a number of verses and sends it straight to your phone.</p>
   <h3 class="description-header">To try out AYAH AID all you have to do is:</h3> 
    <ol class="guide">
      <li>Download the ntfy app ( either from the PlayStore or IOS)</li>
      <br>
      <li>Generate your own unique topic by clicking on the "Generate A Topic" button</li>
      <br>
      <li>Subscribe to the topic you just generated through the app.</li>
      <br>
      <li>Pick A Surah</li>
      <br>
      <li>Pick the number of verses you want to learn/review</li>
      <br>
      <li>Click Send!</li>
    </ol>
  </div> 
</template>
<script lang="ts">
export default {
  name: "SiteDescr",
}
</script>
<style>
h1{
  text-align: center;
  margin: 20px 0px 20px 0px;
}
.description-container > .description-header{
  text-decoration: underline;
  text-align: left;
  margin: 15px 0px 15px 10px;
}
.description-container{
  text-align: center;
}
ol li{
  text-align: left;
  text-wrap: wrap;
}
</style>
