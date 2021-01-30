<template>

  <v-app light>

      <v-container
        class="d-flex"
      >
      <v-col
        md="3"
        align-self="center"
      >
        <v-img
          src="logo.png"
          width="600"
          height="100"
        ></v-img>
      </v-col>

      <v-col
        align-self="center"
      >
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
      </v-col>

      <v-spacer></v-spacer>

        <v-col
        md="3"
        align-self="center"
      >
        <a
          href="https://facebook.com"
          class="fb-ic mr-8" role="button">
          <mdb-icon fab icon="facebook-f" size="lg" />
        </a>

        <a
          href="https://twitter.com"
          class="tw-ic mr-8" role="button">
          <mdb-icon fab icon="twitter" size="lg" />
        </a>

        <a
          href="https://instagram.com"
          class="ins-ic mr-8" role="button">
          <mdb-icon fab icon="instagram" size="lg" />
        </a>
      </v-col>
    </v-container>

    <v-tabs-items  v-model="tab">
      <v-tab-item v-for="item in items" :key="item.tab">
          <v-container fluid>
            <component v-bind:is="item.content"></component>
          </v-container>
      </v-tab-item>
    </v-tabs-items>





    <v-footer
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>

      <v-spacer></v-spacer>

        <v-icon
          @click="darkMode()"
        >{{this.invertColorIcon}}</v-icon>


    </v-footer>

  </v-app>
</template>

<script>
    import { mdbIcon } from 'mdbvue';
    import home from '../components/home';
    import shop from '../components/shop';
    import contact from '../components/contact';
    import about from '../components/about';

    export default {
        components: {
            mdbIcon,
            home,
            shop,
            contact,
            about,
        },
        data () {
            return {
                tab: null,
                items: [
                    { tab: 'Home', content: 'home' },
                    { tab: 'Shop', content: 'Shop' },
                    { tab: 'Contact', content: 'portrait' },
                    { tab: 'About', content: 'about' },
                ],
                isDark: true,
                invertColorIcon: "mdi-invert-colors",
            }
        },
        methods: {
            darkMode() {
                this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
                this.isDark = !this.isDark;
                if(this.isDark){
                    this.invertColorIcon = "mdi-invert-colors"
                }else{
                    this.invertColorIcon = "mdi-invert-colors-off"
                }
            }
        }
    }
</script>
