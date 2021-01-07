<template>
  <div id="top">
    <v-container
      fluid
    >
      <v-card>
        <v-img
          height="800"
          class="white--text align-end text-center font-italic"
          :class="{'headline': $vuetify.breakpoint. smAndDown, 'display-1': $vuetify.breakpoint. mdAndUp}"
          :src="require('@/assets/img/top-img.jpg')"
        >
        <p>Welocome to my Portfolio site</p>
        <p>ようこそ Wang.yu のポートフォリオサイト</p>
        </v-img >
      </v-card>
    </v-container>

  </div>
</template>

<script>

</script>