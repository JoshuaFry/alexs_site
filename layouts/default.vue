<template>

  <v-app light>

    <banner></banner>

    <navBar></navBar>

    <Nuxt/>

    <Footer></Footer>


  </v-app>
</template>

<script>
    import footer from "../components/footer";
    import navBar from "../components/navBar";
    import Banner from "../components/banner";

    export default {
        components: {
            Banner,
            navBar,
            footer,
        },
        data() {
            return {}
        },
    }
</script>
