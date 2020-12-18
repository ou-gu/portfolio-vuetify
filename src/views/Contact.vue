<template>
  <div id="app">
    <v-app>
      <v-card>
        <v-card-title>STEP:0 フォーム</v-card-title>
        <v-card-text>
          <v-text-field
            v-model="text1"
            label="入力必須で文字数制限のあるテキストフィールド"
          >
          </v-text-field>
          <v-text-field
            v-model="text2"
            label="入力必須のみあるテキストフィールド"
          >
          </v-text-field>
          <v-text-field
            v-model="text3"
            label="なんの制約もないテキストフィールド"
          >
          </v-text-field>
        </v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-btn text v-on:click="submit">送信する</v-btn>
          <span v-if="success">送信成功！</span>
        </v-card-actions>
      </v-card>
    </v-app>
  </div>
</template>

<script>
export default {
  
}
</script>