<template>
  <div id="map">

  </div>
</template>

<script>
import * as L from "leaflet";

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  mounted() {
    this.initLeaflet()
  },
  methods:{
    initLeaflet(){
      var map = L.map('map').setView([51.505, -0.09], 13);
////add TianDiTu Normal Map Layer to map.
      L.tileLayer.chinaProvider('TianDiTu.Normal.Map').addTo(map);
      // L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      //   attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
      // }).addTo(map);

      L.marker([51.5, -0.09]).addTo(map)
          .bindPopup('A pretty CSS3 popup.<br> Easily customizable.')
          .openPopup();
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
