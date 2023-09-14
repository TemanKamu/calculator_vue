<template>
  
  <div class="box">
    <div class="screen">
      <screenView @respone="showData" :dataInBtn="dataHasil" />
    </div>
    
    <div class="button">
      <buttonView @respone="sendData" />
    </div>
  </div>

</template> 
<style>
  .box{
    width: 220px;
    background-color: black;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    padding: 5px;
  }
  .button{
    text-align: center;
  }
</style>
<script>
  import buttonView from './components/Button.vue';
  import screenView from './components/Screen.vue';

  export default {
    data(){
      return {
        dataHasil : ""
      }
    },
    components: {
      buttonView,
      screenView
    },
    methods: {
      sendData(data){
        return data == undefined ? this.dataHasil = "0" : this.dataHasil = data
      },
      showData(data){
        return data
      }
    }
  }
</script>