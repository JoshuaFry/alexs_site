<template>

  <v-app light>

    <v-card>

      <v-img src="logo.png"  height="150" contain style="margin-top: 10px"></v-img>

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
    </v-card>


    <v-tabs-items v-model="tab">
        <v-tab-item v-for="item in items" :key="item.tab">
          <v-content fluid >
            <component v-bind:is="item.content"></component>
          </v-content>
        </v-tab-item>
      </v-tabs-items>

  </v-app>
</template>

<script>
    import home from '../components/home';
    import paddles from './paddles';
    import contact from '../components/contact';
    import about from '../components/about';

    export default {
        name: 'navBar',
        components: {
            home,
            paddles,
            contact,
            about,
        },
        data() {
            return {
                tab: null,
                items: [
                    {tab: 'Home', content: 'home'},
                    {tab: 'Paddles', content: 'paddles'},
                    {tab: 'Contact', content: 'contact'},
                    {tab: 'About', content: 'about'},
                ],
            }
        },
    }
</script>
