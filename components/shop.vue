<template>
  <v-col
    cols="12"
    class="flex-center"
  >
    <v-card
      width="800"
    >
      <v-row dense>
        <v-col
          v-for="card in cards"
          :key="card.title"
          :cols="card.flex"
        >
          <paddle-card :title="card.title" :src="card.src" :desc="card.desc">

          </paddle-card>
        </v-col>
      </v-row>

    </v-card>

  </v-col>
</template>

<script>
    import paddleCard from "./paddleCard";

    export default {
        name: 'shop',
        components: {
            paddleCard,
        },
        data: () => ({
            cards: [
                {title: '', src: 'paddles/double.jpg', flex: 6, desc: ""},
                {title: 'Good Vibes', src: 'paddles/good_vibes.jpg', flex: 6, desc: ""},
                {title: 'Malard', src: 'paddles/malard.jpg', flex: 6, desc: ""},
            ],
        }),
    }
</script>
