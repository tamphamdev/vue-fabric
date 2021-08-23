<template>
  <div
    class="hello"
    style="width: 100vw; height: 100vh; background-color: #fff"
  >
    <div id="canvas-container">
      <canvas ref="can"></canvas>
    </div>
  </div>
</template>

<script>
import { fabric } from "fabric";

export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      clientWidth: null,
      clientHeight: null,
    };
  },
  mounted() {
    this.clientWidth = window.innerWidth;
    this.clientHeight = window.innerHeight;
    const ref = this.$refs.can;
    const canvas = new fabric.Canvas(ref);
    // canvas.setDimensions(
    //   {
    //     width: "100%",
    //     height: "100%",
    //   },
    //   {
    //     cssOnly: true,
    //   }
    // );
    let canvasSize = {
      width: 1200,
      height: 700,
    };
    // canvas container dimensions
    let containerSize = {
      width: document.getElementById("canvas-container").offsetWidth,
      height: document.getElementById("canvas-container").offsetHeight,
    };
    let scaleRatio = Math.min(
      containerSize.width / canvasSize.width,
      containerSize.height / canvasSize.height
    );
    canvas.setWidth(containerSize.width);
    canvas.setHeight(containerSize.height);
    canvas.setZoom(scaleRatio);
    const rect = new fabric.Rect({
      fill: "red",
      width: 20,
      height: 20,
    });
    rect.set("selectable", true);
    canvas.add(rect);
  },
};
</script>

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

#canvas-container {
  height: 100vh !important;
  width: 100% !important;
}
</style>
