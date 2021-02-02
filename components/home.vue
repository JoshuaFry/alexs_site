<template>
  <v-card
    :loading="loading"
    class="mx-auto my-12"
    max-width="600"
  >
    <template slot="progress">
      <v-progress-linear
        color="deep-purple"
        height="10"
        indeterminate
      ></v-progress-linear>
    </template>

    <v-img
      height="350"
      src="big_al.jpg"
      contain
    ></v-img>

    <v-card-title>Alex Manard</v-card-title>

    <v-card-text>

      <div class="my-1 subtitle-1">
        Champaign, IL
      </div>

      <div></div>
    </v-card-text>


    <v-divider class="mx-4"></v-divider>

    <v-card-title>Tonight's availability</v-card-title>

    <v-card-text>
      <v-chip-group
        v-model="selection"
        active-class="deep-purple accent-4 white--text"
        column
      >
        <v-chip>5:30PM</v-chip>

        <v-chip>7:30PM</v-chip>

        <v-chip>8:00PM</v-chip>

        <v-chip>9:00PM</v-chip>
      </v-chip-group>
    </v-card-text>

    <v-card-actions>
      <v-btn
        color="deep-purple lighten-2"
        text
        @click="reserve"
      >
        Reserve
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
    export default {
        name: 'home',
        data: () => ({
            loading: false,
            selection: 1,
        }),
        methods: {
            reserve () {
                this.loading = true;

                setTimeout(() => (this.loading = false), 2000)
            },
        },
    }
</script>
