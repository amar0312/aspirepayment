<template>
<q-page class="q-pa-xl col items-start q-gutter-md">
 <div class="row q-pl-md" >
     <div class="col">
     <span style="font-size: 12px;">Available balance</span>
     <div class="col">
     <q-avatar icon="local_atm" size="30px" font-size="30px" color="white" text-color="green" />
     <strong class="q-pa-sm text-h6">{{balance}}</strong>
     </div>
     </div>
     
     <q-space/>
     <div>
         <q-btn icon="add_circle" color="blue-8" label="New Card" size="md" />
     </div>
</div>


</q-page>  
</template>
<script>
export default {
  computed: {
    balance: function() {
      return 3000;
    }
  }
};
</script>
<style>
</style>


