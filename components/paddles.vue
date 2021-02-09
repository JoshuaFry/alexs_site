<template>
  <v-col
    cols="12"
    class="flex-center"
  >
    <v-card
      width="1200"
    >

      <v-card-title>Sports</v-card-title>
      <v-row dense>
        <v-col
          v-for="card in sport_paddles"
          :key="card.title"
          :cols="card.flex"
        >
          <paddle-card :title="card.title" :src="card.src" :desc="card.desc"></paddle-card>
        </v-col>
      </v-row>

      <v-divider></v-divider>

      <v-card-title>Other</v-card-title>
      <v-row dense>
        <v-col
          v-for="card in other_paddles"
          :key="card.title"
          :cols="card.flex"
        >
          <paddle-card :title="card.title" :src="card.src" :desc="card.desc"></paddle-card>
        </v-col>
      </v-row>


    </v-card>
  </v-col>

</template>

<script>
    import paddleCard from "./paddleCard";

    export default {
        name: 'paddles',
        components: {
            paddleCard,
        },
        data: () => ({
            // TODO categorize paddles i.e. sports, ....
            other_paddles: [
                {title: '', src: 'paddles/double.jpg', flex: 6, desc: ""},
                {title: '', src: 'paddles/good_vibes.jpg', flex: 6, desc: ""},
                {title: '', src: 'paddles/malard.jpg', flex: 6, desc: ""},
                {title: '', src: 'paddles/green_white_orange_paddle.jpg', flex: 6, desc: ""},
                {title: '', src: 'paddles/candy.jpg', flex: 6, desc: ""},
                {title: '', src: 'paddles/mounted_western_paddle.jpg', flex: 8, desc: ""},
                {title: '', src: 'paddles/white_blue_paddle.jpg', flex: 6, desc: ""},
                {title: '', src: 'paddles/maroon_orange.jpg', flex: 6, desc: ""},
            ],
            sport_paddles: [
                {title: '', src: 'paddles/green_bay.jpg', flex: 6, desc: ""},
                {title: '', src: 'paddles/iowa.jpg', flex: 6, desc: ""},

            ]
        }),
    }
</script>
