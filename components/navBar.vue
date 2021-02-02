<template>

  <v-app light>

    <v-tabs
      v-model="tab"
      centered
      background-color="transparent"
    >
      <v-tab
        v-for="item in items" :key="item.tab">
        {{ item.tab }}
      </v-tab>
    </v-tabs>

    <v-tabs-items v-model="tab">
      <v-tab-item v-for="item in items" :key="item.tab">
        <v-container fluid>
          <component v-bind:is="item.content"></component>
        </v-container>
      </v-tab-item>
    </v-tabs-items>


  </v-app>
</template>

<script>
    import home from '../components/home';
    import shop from '../components/shop';
    import contact from '../components/contact';
    import about from '../components/about';

    export default {
        name: 'navBar',
        components: {
            home,
            shop,
            contact,
            about,
        },
        data() {
            return {
                tab: null,
                items: [
                    {tab: 'Home', content: 'home'},
                    {tab: 'Shop', content: 'Shop'},
                    {tab: 'Contact', content: 'portrait'},
                    {tab: 'About', content: 'about'},
                ],
            }
        },
    }
</script>
