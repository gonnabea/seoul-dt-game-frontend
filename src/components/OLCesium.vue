<template>
  <div id="cesiumContainer">
    
  </div>
</template>

<script>
// import OLCesium from 'olcs/OLCesium.js';
// import {View} from "ol";
// import Map from 'ol/Map.js';
// import OSM from 'ol/source/OSM';
// import TileLayer from 'ol/layer/Tile';
import * as Cesium from 'cesium';

export default {
  name: 'OLCesium',
  props: {
  
  },
  mounted() {
//     const ol2dMap = new Map({
//   layers: [
    
//     new TileLayer({
//       source: new OSM(),
//     }),
//   ],
//   target: 'map',
//   view: new View({
//     center: [0, 0],
//     zoom: 2,
//   }),
// });


//     const ol3d = new OLCesium({map: ol2dMap}); // ol2dMap is the ol.Map instance
//     ol3d.setEnabled(true);
//     console.log(ol3d)

//     const scene = ol3d.getCesiumScene();

//     console.log(scene)


Cesium.Ion.defaultAccessToken = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJqdGkiOiI4ZjJkMDA4NS0zYmQ2LTQ2NmItOWNjYy03Y2IyMTAwZWNlY2MiLCJpZCI6MTAwNTc3LCJpYXQiOjE2NTcyOTk1NDV9.WcA5OYJ1Cj3S0J30DR6Spb19hx-1bsF3ptiNZDEqKEU';

const worldTerrain = Cesium.createWorldTerrain({
  requestWaterMask: true,
  requestVertexNormals: true,
});

const viewer = new Cesium.Viewer("cesiumContainer", {
  terrainProvider: worldTerrain,
});

// set lighting to true
viewer.scene.globe.enableLighting = true;


var globe = viewer.scene.globe;
globe.enableLighting = true;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
