<template>
    <div id="map-frame" class="relative ml-3">
        <div id="search-animation" class="absolute inset-0 flex items-center justify-center opacity-80 z-1"
            style="background-color: rgba(255,255,255,0.85); width: 98%; height: 100vh;">
        </div>
        <GoogleMap :api-key="API_KEY" :center="center" :zoom="12"
            :style="{ width: '98%', height: '100vh', position: 'absolute' }">
            <Marker :options="{ position: center }" />
        </GoogleMap>
    </div>
</template>
  
<script>
import { GoogleMap, Marker } from 'vue3-google-map'

export default {
    components: {
        GoogleMap,
        Marker
    },
    data() {
        return {
            center: { lat: 29.55, lng: 78.88 },
            anchorCenter: null,
            movementIntervalId: null,
            API_KEY: process.env.VUE_APP_API_KEY
        };
    },
    methods: {
        getCoords() {
            const coords = this.$bus.getData();
            if (coords) {
                this.setTrackedPosition(coords);
            }
        },
        setTrackedPosition(coords) {
            this.anchorCenter = { lat: coords.lat, lng: coords.lng };
            this.center = { lat: coords.lat, lng: coords.lng };
            this.startMovementSimulation();
        },
        startMovementSimulation() {
            this.stopMovementSimulation();
            this.movementIntervalId = window.setInterval(() => {
                if (!this.anchorCenter) {
                    return;
                }

                this.center = {
                    lat: this.getNextCoordinate(this.center.lat, this.anchorCenter.lat),
                    lng: this.getNextCoordinate(this.center.lng, this.anchorCenter.lng)
                };
            }, 10000);
        },
        stopMovementSimulation() {
            if (this.movementIntervalId) {
                window.clearInterval(this.movementIntervalId);
                this.movementIntervalId = null;
            }
        },
        getNextCoordinate(currentValue, anchorValue) {
            const maxOffset = 0.01;
            const step = (Math.random() - 0.5) * 0.002;
            const nextValue = currentValue + step;

            return Math.min(
                anchorValue + maxOffset,
                Math.max(anchorValue - maxOffset, nextValue)
            );
        }
    },
    watch: {
        '$bus.data'(newData) {
            if (newData) {
                this.setTrackedPosition(newData);
            }
        }
    },
    beforeUnmount() {
        this.stopMovementSimulation();
    }
}
</script>  
