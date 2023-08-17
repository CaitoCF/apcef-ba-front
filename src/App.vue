<template>
    <Navbar />
    <Home />
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Home from "./views/Home.vue";
export default {
    components: {
        Navbar,
        Home,
    }
}
</script>

<style>

body {
    background-color: lightgray;
}

* {
    font-family: Helvetica;
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

#app {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
}

@media (pointer:coarse) { 
    #app {
        position: fixed;
        height: 100%;
        width: 100%;
    }
}

</style>
