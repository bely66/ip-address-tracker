<template>
 <div class="ip-tracker-page">
  <div fluid class="header">
    <div class="ip-search-bar">
      <SearchBar />
    </div>
  </div>
  <div class="map-section">
    <l-map
      :zoom="zoom"
      :center="center"
      style="height: 200px; width: 100%"
    >
      <l-tile-layer
        :url="url"
        :attribution="attribution"
      />
      <l-control class="example-custom-control">
        <p @click="showAlert">
          Click me
        </p>
      </l-control>
      <l-control
        :position="'bottomleft'"
        class="custom-control-watermark"
      >
        Vue2Leaflet Watermark Control
      </l-control>
    </l-map>
  </div>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar.vue'
import { latLng } from "leaflet";
import { LMap, LTileLayer, LControl } from "vue2-leaflet";



export default {
  name: 'App',
  components: {
    SearchBar,
    LMap,
    LTileLayer,
    LControl,
  },
  data() {
    return {
      zoom: 13,
      center: latLng(47.41322, -1.219482),
      url: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
      attribution:
        '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors'
    };
  },
  methods: {
    showAlert() {
      alert("Click!");
    }
  }
};
</script>

<style>
.ip-tracker-page{
  display: grid;
}

.header{
  position: absolute;
  top:0;
  right:0;
  left:0;
  margin:0;
  width: 100%;
  height: 17em;
  background-image: url(assets/pattern-bg.png);
  align-content: center;
  align-items: center;
}

.ip-search-bar{
  position: relative;
  padding: 6em;
}


.example-custom-control {
  background: #fff;
  padding: 0 0.5em;
  border: 1px solid #aaa;
  border-radius: 0.1em;
}
.custom-control-watermark {
  font-size: 200%;
  font-weight: bolder;
  color: #aaa;
  text-shadow: #555;
}
</style>
