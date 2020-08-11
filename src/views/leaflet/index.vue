vue
<template>
  <div id="mapid" class="map"></div>
</template>

<script>
import L from 'leaflet';
import 'leaflet/dist/leaflet.css';

export default {
  name: 'Leaflet',
  data() {
    return {
      map: null
    };
  },
  mounted() {
    this.map = L.map('mapid').setView([36.49771311230842, 109.45744048529967], 13);
    // 加载谷歌地图
    L.tileLayer('http://mt0.google.cn/vt/lyrs=m@160000000&hl=zh-CN&gl=CN&src=app&y={y}&x={x}&z={z}&s=Ga', {
      attribution: '© <a href="http://osm.org/copyright">OpenStreetMap</a> contributors'
    }).addTo(this.map);
    // 加载高德地图
    L.tileLayer('http://webrd0{s}.is.autonavi.com/appmaptile?x={x}&y={y}&z={z}&lang=zh_cn&size=1&scale=1&style=8', { subdomains: '1234' }).addTo(this.map);
    // L.marker([data.lat, data.lng]).addTo(this.map);
    // L.circle([data.lat, data.lng], { color: 'red', fillColor: '#f03', fillOpacity: 0.5, radius: 3 }).addTo(this.map);
  }
};
</script>
<style lang="scss" scoped>
.map {
  width: 100%;
  min-height: calc(100vh - 84px);
}
</style>
