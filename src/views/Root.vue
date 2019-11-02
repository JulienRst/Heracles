<template>
  <div ref="root" id="root">
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';
import * as THREE from 'three';

@Component({
  name: 'Root'
})
export default class Root extends Vue {
  private scene: THREE.Scene = new THREE.Scene();
  private camera: THREE.PerspectiveCamera = new THREE.PerspectiveCamera( 75, window.innerWidth / window.innerHeight, 0.1, 1000 );
  private renderer: THREE.WebGLRenderer = new THREE.WebGLRenderer();

  public mounted () {
    const root = this.$refs['root'];
    root.append(this.renderer.domElement);
  }
}
</script>
