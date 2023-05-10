<template>
<!-- template root는 하나의 element만 있어야 한다. -->
  <div>
    <AppHeader 
    :propsdata="str"
    @renew="renewStr"
    ></AppHeader>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';

export default {
  data: function() {
    return {
      isHeaderState : true,
      str : 'Header'
    }
  },
  components : {
    AppHeader,
  },
  methods: {
    renewStr: function() {
      if(this.isHeaderState){
        this.str = 'Hi';
        this.isHeaderState = false;
      } else {
        this.str = 'Header';
        this.isHeaderState = true;
      }
    }
  }
}
</script>

<style>

</style>