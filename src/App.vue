<template>
    <nav id="mynav" style="flex-direction: row;" class="nav">
        <router-link to="/">Home</router-link>
        <router-link to="/if">If</router-link>
    </nav>
    <router-view />
</template>

<script setup>
import {inject, ref, reactive, onMounted, watch, computed} from "vue";
const $axios = inject('$axios');

const getList  = async () => {
    let rtn = await $axios.get("/v1/select");
    if(rtn.status === 200) {
        console.log(rtn);
    }
};
</script>


<style scoped>
/*.logo {*/
/*  height: 6em;*/
/*  padding: 1.5em;*/
/*  will-change: filter;*/
/*  transition: filter 300ms;*/
/*}*/
/*.logo:hover {*/
/*  filter: drop-shadow(0 0 2em #646cffaa);*/
/*}*/
/*.logo.vue:hover {*/
/*  filter: drop-shadow(0 0 2em #42b883aa);*/
/*}*/

/*#app {*/
/*    font-family: Avenir, Helvetica, Arial, sans-serif;*/
/*    -webkit-font-smoothing: antialiased;*/
/*    -moz-osx-font-smoothing: grayscale;*/
/*    text-align: center;*/
/*    color: #2c3e50;*/
/*    margin-top: 20px;*/
/*}*/

.nav {display:flex;background:indigo; padding: 8px 20px;}
.nav a {margin: 5px 20px; font-size:16px; color:white; text-decoration:none;}
</style>
