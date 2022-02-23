<template>
  <q-page class="q-pa-xl col items-start q-gutter-md">
  
  
  
    <div class="row q-pl-md">
  
  
  
      <div class="col">
  
  
  
        <span style="font-size: 12px;">Available balance</span>
  
  
  
        <div class="col">
  
  
  
          <q-avatar icon="local_atm" size="30px" font-size="30px" color="white" text-color="green" />
  
  
  
          <strong class="q-pa-sm text-h6">{{balance}}</strong>
  
  
  
        </div>
  
  
  
      </div>
  
  
  
  
  
  
  
      <q-space/>
  
  
  
      <div>
  
  
  
        <q-btn icon="add_circle" color="blue-8" label="New Card" size="md" @click="alert=true" />
  
        <q-dialog v-model="alert">
  
          <q-card>
  
            <q-card-section>
  
              <div class="text-h6">Alert</div>
  
            </q-card-section>
  
  
  
            <q-card-section class="q-pt-none">
  
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum repellendus sit voluptate voluptas eveniet porro. Rerum blanditiis perferendis totam, ea at omnis vel numquam exercitationem aut, natus minima, porro labore.
  
            </q-card-section>
  
  
  
            <q-card-actions align="right">
  
              <q-btn flat label="OK" color="primary" v-close-popup />
  
            </q-card-actions>
  
          </q-card>
  
        </q-dialog>
  
  
  
      </div>
  
  
  
    </div>
  
  
  
    <div class="q-pa-xs" style="max-width: 300px">
  
  
  
      <q-tabs v-model="tab" no-caps narrow-indicator dense inline-label class="text-grey" active-color="black" align="justify" indicator-color="green">
  
  
  
        <q-tab name="debitcard" label="My debit cards" />
  
  
  
        <q-tab name="allcard" label="All company cards" />
  
  
  
      </q-tabs>
  
  
  
    </div>
  
  
  
    <div class="q-pa-xs">
  
  
  
      <q-card>
  
  
  
        <div class="q-pa-lg row ">
  
  
  
          <div class="col q-gutter-lg">
  
            <!-- <div class="text-green q-gutter-xs" style="text-align:center"><q-icon name="visibility" />
  
  <span>Show card number</span></div> -->
  
  
  
            <q-carousel v-model="slide" swipeable animated :control-type="controlType" control-color="green" navigation height="250px" padding class="text-purple rounded-borders">
  
  
  
              <q-carousel-slide name="style" class="column no-wrap flex-center">
  
                <q-space/>
  
                <div class="text-green q-pr-xl q-gutter-xs absolute-right" style="float: right">
  
                  <q-icon name="visibility" />
  
                  <strong>Show card number</strong></div>
  
                <div class="q-pa-sm"></div>
  
                <q-card class="bg-green">
  
                  <q-card-section style="height:180px; width:300px">
  
                  </q-card-section>
  
                </q-card>
  
              </q-carousel-slide>
  
              <q-carousel-slide name="tv" class="column no-wrap flex-center">
  
                <q-card class="bg-yellow">
  
                  <q-card-section style="height:180px; width:300px">
  
                  </q-card-section>
  
                </q-card>
  
              </q-carousel-slide>
  
            </q-carousel>
  
  
  
            <q-card style="max-width: 500px; width: 100%;">
  
  
  
              <q-card-section>
  
                <q-btn icon="mdi-snowflake-alert" flat color="blue-8" label="Freez card" size="sm" stack />
  
                <q-btn icon="speed" flat color="blue-8" label="Set spend limit" size="sm" stack/>
  
                <q-btn icon="mdi-google" flat color="blue-8" label="Add to GPay" size="sm" stack />
  
                <q-btn icon="replay" flat color="blue-8" label="Replace card" size="sm" stack />
  
                <q-btn icon="delete" flat color="blue-8" label="Cancel card" size="sm" stack />
  
  
  
              </q-card-section>
  
  
  
            </q-card>
  
          </div>
  
  
  
          <div class="col">
  
            <q-list bordered class="rounded-borders">
  
              <q-expansion-item expand-separator icon="payment" label="Card details">
  
                <q-card>
  
                  <q-card-section>
  
                    Filled with Card Details
  
                  </q-card-section>
  
                </q-card>
  
              </q-expansion-item>
  
              <q-separator />
  
              <q-expansion-item expand-separator icon="swap_horiz" label="Recent transactions">
  
                <q-card>
  
                  <q-card-section>
  
                    Filled with Recent Transaction
  
                  </q-card-section>
  
                </q-card>
  
              </q-expansion-item>
  
            </q-list>
  
  
  
          </div>
  
  
  
        </div>
  
  
  
      </q-card>
  
  
  
    </div>
  
  
  
  
  
  
  
  
  
  
  
  </q-page>
</template>
<script>
export default {
  data() {
    return {
      tab: "debitcard",

      slide: "style",

      alert: false
    };
  },

  computed: {
    balance: function() {
      return 3000;
    }
  }
};
</script>
<style>
</style>


