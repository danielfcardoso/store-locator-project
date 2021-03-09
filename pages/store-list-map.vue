<template>
  <div>
    <div>
      <vl-map
        :load-tiles-while-animating="true"
        :load-tiles-while-interacting="true"
        data-projection="EPSG:4326"
        style="height: 500px"
      >
        <vl-view :zoom.sync="zoom"/>
        <vl-geoloc @update:position="geolocPosition = $event">
          <template slot-scope="geoloc">
            <vl-feature v-if="geoloc.position" id="position-feature">
              <vl-geom-point :coordinates="geoloc.position" />
              <vl-style-box>
                <vl-style-icon src="_media/marker.png" :scale="0.4" :anchor="[0.5, 1]" />
              </vl-style-box>
            </vl-feature>
          </template>
        </vl-geoloc>

        <vl-layer-tile id="osm">
          <vl-source-osm />
        </vl-layer-tile>
      </vl-map>
    </div>
  </div>
</template>

<script>
export default {
  name: 'StoreList',
  data () {
    return {
      zoom: 5,
      geolocPosition: undefined
    }
  }
}

</script>

<style scoped>

</style>
