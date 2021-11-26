<template>
  <div class="wrapper">
    <div class="cakeBox">
      <div
        class="cakeLayer"
        v-for="layer in layers"
        v-bind:key="layer"
        v-bind:style="{
          borderRadius: layer.br + 'px',
        }"
      >
        <div
          class="layerGroup"
          v-for="l in layer.count"
          v-bind:key="l"
          v-bind:style="{
            backgroundImage: 'url(' + layer.bg + ')',
            backgroundSize: layer.bgsize,
            backgroundRepeat: layer.bgrepeat,
            height: layer.size + 'px',
            width: layer.width + 'px',
          }"
        >
          <div class="layer">
            <!-- {{ layer.bgrepeat }} -->
          </div>
        </div>
      </div>
    </div>
    <div class="cakeTools">
      <div class="cakeToolGroup" v-for="lt in layers" v-bind:key="lt">
        <div class="input_group">
          <label>background-image</label>
          <input type="text" v-model="lt.bg" />
        </div>
        <div class="input_group">
          <label>background-size</label>
          <input type="text" v-model="lt.bgsize" />
        </div>
        <div class="input_group">
          <label>background-repeat</label>
          <select v-model="lt.bgrepeat">
            <option selected value="repeat">repeat</option>
            <option value="no-repeat">no-repeat</option>
            <option value="repeat-x">repeat-x</option>
            <option value="repeat-y">repeat-y</option>
          </select>
        </div>
        <div class="input_group">
          <label>size</label>
          <input type="number" v-model="lt.size" />
        </div>
        <div class="input_group">
          <label>width</label>
          <input type="number" v-model="lt.width" />
        </div>
        <div class="input_group">
          <label>count</label>
          <input type="number" v-model="lt.count" />
        </div>
        <div class="input_group">
          <label>border-radius</label>
          <input type="number" v-model="lt.br" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Caker",
  data() {
    return {
      layers: [
        {
          size: 60,
          width: 60,
          count: 1,
          br: 10,
          bgsize: "contain",
          bgrepeat: "no-repeat",
          bg: "https://i.ya-webdesign.com/images/cherry-png-1.png",
        },
        {
          size: 30,
          width: 333,
          count: 3,
          br: 10,
          bgsize: "contain",
          bgrepeat: "repeat",
          bg:
            "https://catherineasquithgallery.com/uploads/posts/2021-02/1613156755_113-p-zheltii-fon-sladosti-207.jpg",
        },
        {
          size: 80,
          width: 444,
          count: 2,
          br: 5,
          bgsize: "contain",
          bgrepeat: "repeat",
          bg:
            "https://avatars.mds.yandex.net/i?id=0f6e6b5d0e4ac144f853d7ccb9134bda-5858829-images-thumbs&n=13",
        },
        {
          size: 5,
          width: 666,
          count: 30,
          br: 10,
          bgsize: "contain",
          bgrepeat: "repeat",
          bg:
            "https://catherineasquithgallery.com/uploads/posts/2021-02/1612318865_93-p-shokoladnaya-plitka-fon-130.jpg",
        },
      ],
    };
  },
  methods: [],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  transition: all 1s;
}
h3 {
  margin: 20px 0 0;
}
a {
  color: #42b983;
}
.wrapper {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-evenly;
}
.cakeBox {
  display: flex;
  flex-direction: column;
  min-width: 666px;
}
.cakeLayer {
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  overflow: hidden;
}
.layerGroup {
  display: flex;
  background-position: center;
}

/* инпуты */

.cakeTools {
  display: flex;
  /* flex-direction: column; */
}

.input_group {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 10px;
  padding-top: 0;
  max-width: 160px;
}

.input_group input,
.input_group select {
  padding: 3px;
  border-radius: 6px;
  border: 1px solid #42b983;
  background-color: #fff;
  font-size: 16px;
  width: 100%;
}

.input_group label {
  font-size: 14px;
  color: #42b983;
  text-transform: lowercase;
}
</style>
