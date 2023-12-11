<template>
  <div class="tfs-pic-container">
    <tfsStatus v-model:meterNum="meters"></tfsStatus>
    <TfsPic></TfsPic>
  </div>
  <div class="tfs-button-container">
    <TfsButton @click="handleWater"><font-awesome-icon :icon="['fas', 'droplet']" /> Water</TfsButton>
    <TfsButton @click="handleFertilize" color="#8b4a00" colorHover="#b35f00" colorActive="#8b4a00"><font-awesome-icon
        :icon="['fas', 'poop']" /> Fertilize</TfsButton>
  </div>
</template>

<script>
import TfsButton from './components/tfs-button.vue';
import TfsPic from './components/tfs-pic.vue';
import tfsStatus from './components/tfs-status.vue';

export default {
  name: 'app',
  components: {
    TfsButton,
    TfsPic,
    tfsStatus
  },
  data() {
    return {
      meters: 0
    }
  },
  methods: {
    handleWater() {
      console.log('浇水');
      if (this.meters >= 2147483647) {
        alert('别浇了别浇了快顶破天了！');
        return;
      }
      this.meters += 1;
    },
    handleFertilize() {
      console.log('施肥');
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Noto+Sans+SC');
@import url('https://fonts.googleapis.com/css?family=Josefin+Sans');

.tfs-button-container {
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

.tfs-pic-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-top: 20px;
}

* {
  font-family: Noto Sans SC;
}
</style>