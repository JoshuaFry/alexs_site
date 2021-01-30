<template>

  <v-app light>

      <v-tabs
        v-model="tab"
      >

        <v-container
          float
          class="d-flex flex-row"
        >

          <v-spacer></v-spacer>
          <v-spacer></v-spacer>

          <v-tab
            v-for="item in items" :key="item.tab">
            {{ item.tab }}
          </v-tab>

          <v-spacer></v-spacer>

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

          </v-container>
      </v-tabs>


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
