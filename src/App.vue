<template>
  <div id="app">
    <Principal vm-icon="access_alarm" vm-label="Titulo de teste do comp" vm-description="Sabia ele que todo mundo fazia esse tipo de teste ao tentar realizar algo fjrfjrfj fjiroifj roifjrijfiorj">
      <a class="waves-effect waves-light btn-small red"><i class="material-icons right">cloud</i>button</a>
    </Principal>
  </div>
</template>

<script>
  import Principal from "./components/Principal";

export default {
  name: 'App',
  components: {
    Principal
  },
  data(){
    return{
    }
  }
}
</script>

<style>
</style>
