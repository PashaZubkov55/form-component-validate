<template>
  <div id="app">
  <div class="container">
    <div class="container__wrapper">

    <div class="text">
      <div class="text__wrapper">
        <div class="text__title"><h1>Liarn to code by<br/> wathing others</h1></div>
        <div class="text__description">
          See no exprenced developers solve  problems in real time<br/> 
          wathing scripted tutoreals is great but understending how <br/>
          developers think is invaluable
          </div>
          <div class="text__description  text__description-mobile">
          See no exprenced developers solve  problems in real time 
          wathing scripted tutoreals is great but understending how 
          developers think is invaluable
          </div>
      </div>
    </div>
    <formComponent />

    
    </div>
  </div>
  </div>
</template>

<script>
import formComponent from "./components/form.vue";
export default {
 components:{
   formComponent
 }
}
</script>
<style>

@import"./assets/style.css";

</style>

