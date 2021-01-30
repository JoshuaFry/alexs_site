<template>

  <v-app light>

    <v-container
    >
      <v-row
        md="12"
      >
      <v-col
        md="3"
        align-self="center"
      >
        <v-img
          src="logo.png"
          width="600"
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
    </v-row>
    </v-container>



    <v-tabs-items  v-model="tab">
      <v-tab-item v-for="item in items" :key="item.tab">
        <v-card flat>
          <v-card-text>
            <component v-bind:is="item.content"></component>
          </v-card-text>
        </v-card>
      </v-tab-item>
    </v-tabs-items>


    <v-footer
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>

    </v-footer>

  </v-app>
</template>

<script>
    import { mdbIcon } from 'mdbvue';

    export default {
        components: {
            mdbIcon
        },
        data () {
            return {
                tab: null,
                items: [
                    { tab: 'Home', content: 'home' },
                    { tab: 'Shop', content: 'Shop' },
                    { tab: 'Contact', content: 'portrait' },
                    { tab: 'About', content: 'about' },
                ]
            }
        }
    }
</script>
