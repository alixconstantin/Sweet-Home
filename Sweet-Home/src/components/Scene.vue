<template>
    <div ref="container"></div>
  </template>
  
  <script>
  import * as THREE from 'three';
  import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls.js';
  import stoneTexture from '../images/stone.png';
  import boxTexture from '../images/box.jpeg';
  
  export default {
    mounted() {
      // Create Scene
      const scene = new THREE.Scene();
      scene.background = new THREE.Color(0x202022);
  
      // Create Camera
      const camera = new THREE.PerspectiveCamera(
        75,
        760 / 760,
        0.1,
        1000
      );
      camera.position.set(0, 0, 5);
  
      // Create Renderer
      const renderer = new THREE.WebGLRenderer();
      renderer.setSize(760, 760);
      renderer.shadowMap.enabled = true;
      renderer.shadowMap.type = THREE.PCFSoftShadowMap;
      this.$refs.container.appendChild(renderer.domElement);
  
      // Add Light
      /*
      const light = new THREE.DirectionalLight(0xffffff, 1.5);
      light.position.set(0, 1, -1).normalize();
      light.castShadow = true;
      light.shadow.mapSize.width = 1024;
      light.shadow.mapSize.height = 1024;
      light.shadow.camera.near = 0.1;
      light.shadow.camera.far = 500; 


      const lightHelper = new THREE.DirectionalLightHelper(light, 1);

      scene.add(lightHelper);
      scene.add(light); */
      const light = new THREE.DirectionalLight(0xffffff, 0.2);
      light.position.set(0, 1, -1).normalize();
      light.castShadow = true;
      scene.add(light);
      var ambientLight = new THREE.AmbientLight(0xffffff, 2.5);
      scene.add(ambientLight);
  
      // Add Object
      const geometry = new THREE.BoxGeometry(1, 1, 1);
      const texture = new THREE.TextureLoader().load(boxTexture);
      const material = new THREE.MeshStandardMaterial({
        map: texture,
        roughness: 0.9,
        metalness: 0.6,
      });
      const mesh = new THREE.Mesh(geometry, material);
      mesh.castShadow = true;
      mesh.receiveShadow = true;
      mesh.position.set(0,-1,0)
      scene.add(mesh);
  
      // Add Ground
      const planeGeometry = new THREE.PlaneGeometry(5, 5);
      const planeMaterial = new THREE.MeshStandardMaterial({
        map: texture,
        roughness: 0.5,
        metalness: 0.5,
      });
      const plane = new THREE.Mesh(planeGeometry, planeMaterial);
      plane.receiveShadow = true;
      plane.rotation.x = -Math.PI / 2;
      plane.position.set(0,-3)
      scene.add(plane);

      
  
      // Add Controls
      const controls = new OrbitControls(camera, renderer.domElement);
      controls.enableDamping = true;
      controls.update();
  
      // Animate
      const animate = () => {
        requestAnimationFrame(animate);
  
        mesh.rotation.x += 0.005;
        mesh.rotation.y += 0.005;
  
        renderer.render(scene, camera);
      };
      animate();
    },
  };
  </script>
  
  <style>
    canvas {
      width: 100%;
      height: 100%;
    }
  </style>
  