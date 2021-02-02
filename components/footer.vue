<template>
  <v-footer
    app
  >

    <span>&copy; {{ new Date().getFullYear() }}</span>

    <v-spacer></v-spacer>

    <div class="d-flex flex-row">
      <div class="p-2">
        <a
          href="https://facebook.com"
          class="fb-ic mr-8" role="button">
          <mdb-icon fab icon="facebook-f" size="lg"/>
        </a>

        <a
          href="https://twitter.com"
          class="tw-ic mr-8" role="button">
          <mdb-icon fab icon="twitter" size="lg"/>
        </a>

        <a
          href="https://instagram.com"
          class="ins-ic mr-8" role="button">
          <mdb-icon fab icon="instagram" size="lg"/>
        </a>
      </div>
    </div>

    <v-spacer></v-spacer>

    <v-icon
      @click="darkMode()"
    >{{this.invertColorIcon}}
    </v-icon>


  </v-footer>
</template>

<script>
    import {mdbIcon} from 'mdbvue';

    export default {
        name: 'Footer',
        components: {
            mdbIcon,
        },
        data() {
            return {
                isDark: true,
                invertColorIcon: "mdi-invert-colors",
            }
        },
        methods: {
            darkMode() {
                this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
                this.isDark = !this.isDark;
                if (this.isDark) {
                    this.invertColorIcon = "mdi-invert-colors"
                } else {
                    this.invertColorIcon = "mdi-invert-colors-off"
                }
            }
        }
    }
</script>
