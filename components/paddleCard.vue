<template>

    <v-card
      elevation="4"
    >

      <v-img
        :v-if={src}
        :src={src}
        class="white--text align-end"
      >

        <v-card-title>{{title}}</v-card-title>

      </v-img>

<!--      <v-card-text>-->
<!--        <div>{{desc}}</div>-->
<!--      </v-card-text>-->

    </v-card>


</template>

<script>
    export default {
        name: 'paddleCard',
        props: [
            'src',
            'desc',
            'title',
        ]
    }
</script>
