<template>
    <div id="nav">
        <router-link to="/" class="routerlink"><img alt="APCEF LOGO" src="https://doc-08-8c-docs.googleusercontent.com/docs/securesc/iss0hal64flosvcsa5uhf4jh1iprsr11/aln63mng7po36vpr37bem26n229s8pk6/1693435575000/09432904667941162152/09432904667941162152/182PWUWD5PRLJri244jiIT2PJm6wNOreS?e=download&ax=AH3YgiBFhq-VmMXTyLbeeadrA079W3Cd41cuXW9Vu4xA6WRf2YGRLm-h3S-dINMiAkP-cP1ibKpnH5tKKxjCzBBdhIpaImd64l6f0eMG600CnWKdr2r3D3WtTSyN3X-b7hW7oEdQRHLe0LBgfMEFc0a48n5agFiBLgGnigp2v0sWR3RvsWUTD2mllzP9CaZ8CmsjNfvGAqxPTav2aB64iKu90IYWLdoAWpREhQlxkITR0HaKoiKsc4drm62IUXp8kv4sZvMchSLFLbtLL2cqExInDO1P83lr6K3xTRdxaImba-6wFP2PzAXNf3hx7PbM9g-K8jepm5SA_mC9FrKmBUUwVP_Yu5A8wM5D0HA9_uqmfMGnBRNyo45jVI4jXqqdh2-N4FGhkuZ5WdrNkhLHOshxt7TqRSfjqHPvz1_7eQuALvvD8ZiMMVesQJDA4ur1Qon_3dJGaIqw2Xzko5j3kSp7fdGig9tsCwig7fd56ALDMWEPnPub6MKCQPXsn2sf1Hx7nxbzsfFwL1ybJvu6KSCEb-d2ELd2kHfvVaS5jMTjOdquKuzcBvK1gB832n55aycEJ-AlaHVLVcDB3-SpQ5mkUIdLQGavvAg0lIstVpmoSTkMaEcC1ZkR1ODialh58txidzPN0p7JCJzvMfxRB5mQxEWFbOZPYoKY6-RY0AJbdXeZ_lglZLu8tE8_xqCINqXuMbWetW5CXZb2m4P7t5XwNMY2nPzLQKFS2OaOrwPf0bVP16JpfOnA-b9mGwZSY_Se2l_AjKx1Bb5V3Chf_ki4UFKoqHVV_DDk1qvjqlY0THuQ19gXTTrpSJ4vYVVwVllvkGk0SwDsY7cvgTPaB6I2-ON9oEBQ4qa1roz20ZUzJPigT9e9vbSC8ua3H8flrUgYiX6G9_ijP-ckMf_u1pumKYtLAVQ6w2q_vYQD&uuid=9629316e-bd6a-4885-850f-f299a0ae5b41&authuser=0&nonce=574lrljjskpga&user=09432904667941162152&hash=8v11ttfdl0r1mqk7000fd0kia72hsmu9" id="logo"></router-link>
        <p>XII JOGOS DO NODESTE 2023</p>
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
        font-size: 21px;
        margin-left: 4%;
        color: #ffffff;
        font-weight: bolder;
    }
}

</style>
