<template>
    <div id="nav">
        <router-link to="/" class="routerlink"><img alt="APCEF LOGO" 
            src="https://firebasestorage.googleapis.com/v0/b/apcef-ba-stg.appspot.com/o/Logo.png?alt=media&token=9b99aa72-adeb-4839-92fc-7841757e00c9" id="logo"></router-link>
        <p>XII JOGOS DO NORDESTE 2023</p>
    </div>
</template>

<script>
export default {
    name: "nav-bar",
}
</script>

<style scoped>

#nav {
    background-color: #163573;
    position: relative;
    left: 50%;
    transform: translateX(-50%);
    width: 50%;
    z-index: 1;
    height: 10vh;
    display: flex;
    align-items: center;
}

#logo {
    width: 90%;
    position: relative;
    right: 10%;
}

.routerlink {
    width: 20%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: start;
}

p {
    font-size: 40px;
    color: #ffffff;
    font-weight: bolder;
}

@media (pointer:coarse) { 
    #nav {
        left: 0%;
        transform: translateX(0%);
        width: 100%;
        height: 15vh;
    }

    #logo {
        width: 150%;
    }

    p {
        font-size: 19px;
        margin-left: 4%;
        color: #ffffff;
        font-weight: bolder;
    }
}

</style>
