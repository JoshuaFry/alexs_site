<template>

  <v-app light>

<!--    <banner></banner>-->

    <navBar>
      <Nuxt></Nuxt>
    </navBar>

    <customFooter></customFooter>

  </v-app>

</template>

<script>
    import customFooter from "../components/customFooter";
    import navBar from "../components/navBar";
    import Banner from "../components/banner";

    export default {
        components: {
            Banner,
            navBar,
            customFooter,
        },
        data() {
            return {}
        },
    }
</script>
