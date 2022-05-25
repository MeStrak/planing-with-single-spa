<template>
  <div class="py-3">
    <h1 class="h1-vue">I am an application</h1>
      <!-- <input type="text" placeholder="Filter by department or employee" v-model="filter" /> -->

    <div id="parcel"></div>
    <br /><br />
    <div id="parcel2"></div>

  </div>
</template>

<script>
//import { mountRootParcel } from 'single-spa';
import { mountParcel } from '../main.js'

export default {
  name: 'parcelPage',
  mounted() {
      this.loadParcel()
  },
  methods: {
      loadParcel() {
        var domElement = document.getElementById('parcel')
        /*global System*/
        mountParcel(() => System.import("sample-vue-parcel"), { domElement })
        //mountRootParcel(() => System.import("sample-react-parcel"), { domElement })

        domElement = document.getElementById('parcel2')
        /*global System*/
        mountParcel(() => System.import("vue-parcel2"), { domElement })
      }
  }
}
</script>

<style scoped>
input[type=text], select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  margin-top: 25px;
}
</style>