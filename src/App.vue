<script setup>
import HelloWorld from './components/HelloWorld.vue'
// import init, { add, address_from_public_key } from 'anychain-wasm';
import init, { decode_invoice } from 'bitlight-utils';
import {onMounted} from 'vue';
onMounted( () => {
  init().then( () => {
    // let sum = add(2,3);
    // console.log(sum);
    // let pub_key = "0x0299bb27e93fba02d13d78b1d7807cc811266e31e7b6feae3e09d42d49482fda95";
    // let pub_addr = address_from_public_key(pub_key);
    // console.log("public address is:", pub_addr);
    let invoice_str = "rgb:2wRu3Ky-aEnB8QF6z-WC821epvQ-ucf3R6fzH-QpRntUXb4-Hp3VEKJ/RGB20/1000+tb1pz7994vg9lktzmhs437f65x96t09k5vecju8gmj8jguswav5el6wqnhfz5z";
    let invoice = decode_invoice(invoice_str);
    console.log("invoice address is:", invoice);

  })
})
</script>

<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <HelloWorld msg="Vite + Vue" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
