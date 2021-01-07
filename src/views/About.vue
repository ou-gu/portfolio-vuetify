<template>
  <div id="about">
    <v-container fluid>
      <v-card width="100vw" class="pa-4">
        <v-card-title>
          <h1 class="pagetitle display-3 font-weight-bold mt-8 mb-8">
            About me
          </h1>
        </v-card-title>

        <v-card>
          <v-card-actions class="justify-center">
            <v-avatar
              color="grey"
              size="300"
              class="elevation-4 mt-n10 my-icon"
            >
              <v-img :src="require('@/assets/img/monster01.png')" />
            </v-avatar>
          </v-card-actions>
          <v-card-title primary-title>
            <div>
              <span class="display-1 font-weight-bold mb-1">{{ myname }}</span>
            </div>
          </v-card-title>

          <div class="px-2">

            <v-card-text>
              <v-list dark two-line>
                <v-list-item-group>
                  <v-list-item
                    v-for="activity in activities"
                    :key="activity.name"
                  >
                    <v-list-item-avatar>
                      <v-icon class="teal">{{ activity.icon }}</v-icon>
                    </v-list-item-avatar>

                    <v-list-item-content>
                      <v-list-item-title>{{ activity.text }}</v-list-item-title>
                      <v-list-item-subtitle>{{
                        activity.subtext
                      }}</v-list-item-subtitle>
                    </v-list-item-content>
                  </v-list-item>
                </v-list-item-group>
              </v-list>
            </v-card-text>
          </div>
        </v-card>
        <v-timeline>
          <v-timeline-item
            v-for="(year, i) in years"
            :key="i"
            :color="year.color"
            small
          >
            <template>
              <span
                :class="`title font-weight-bold ${year.color}--text`"
                v-text="year.year"
              ></span>
            </template>
            <div class="py-4">
              <h2 :class="`title font-italic mb-4 ${year.color}--text`">
                {{ year.title }}
              </h2>
              <div>
                {{ year.content }}
              </div>
            </div>
          </v-timeline-item>
        </v-timeline>
      </v-card>
    </v-container>
  </div>
</template>

<script>
export default {
  data: () => ({
    myname: "王寓（Wang.yu）",
    activities: [
      {
        text: "好きなこと",
        subtext:
          "食べることが大好きで、特に甘いもの好きで暇なときにタルトを自分で焼いたりしてます。",
        icon: "mdi-cake-variant",
      },
      {
        text: "ボルダリング",
        subtext:
          "趣味は体を動かすことです、ボルダリングなどで体を動かして頭をリフレッシュしています。",
        icon: "mdi-image-filter-hdr",
      },
      {
        text: "やりたい事",
        subtext:
          "場所に縛られずに仕事がしたい、世界を回りながら仕事をするのが目標です。",
        icon: "mdi-airplane-takeoff",
      },
      {
        text: "プログラミング",
        subtext:
          "インフラとデータベースについての理解が足りないため、今後はデータベースを絡めたアプリを開発したいです。",
        icon: "mdi-iframe",
      },
      {
        text: "今後の展望",
        subtext:
          "中国生まれ、日本育ちとして両国の関係に何かしらいい影響を与えられる人材になりたいと考えています。",
        icon: "mdi-binoculars",
      },
    ],
    years: [
      {
        color: "cyan",
        year: "1992-7-11",
        title: "福建省で誕生",
        content:
          "中国の四季折々で自然が豊かな農村部に生まれました、山の中を自由に駆け回っていました。この時から食い意地は人一倍強い子でした。",
      },
      {
        color: "pink",
        year: "2012-2014",
        title: "工学院大学",
        content:
          "大学では環境工学を勉強していました。研究室では逆浸透膜（RO）の研究に携わっていました。幼少期は自然豊かな場所で育ったため、将来的には環境浄化などのプジェクトに携わりたいと考えています。",
      },
      {
        color: "amber",
        year: "2016-2020",
        title: "プラントエンジニアとして就職",
        content:
          "一年目から中国の安徽省で台湾系の半導体メーカーと一緒に工場を立ち上げる業務に携わっていました、一年目の業務は主に材料や装置の受け入れて、数量・規格・品質に問題がないことを確認することでした。二つ目のプロジェクトは中国のメーカーで業務は主に施工管理に携わっていました。施工の納期、品質などを厳しく確認していました。三つ目のプロジェクトは韓国の半導体メーカーに納める装置の基本設計や装置の選定に携わっていました。",
      },
      {
        color: "grey",
        year: "2020-10",
        title: "現在",
        content:
          "単純作業の業務が多くなんとか効率化できないのかと考えプログラミングに興味を持ち始めました、その後独学でプログラミングを勉強するに連れてエンジニアに転身したいという思いが強くなり、4年半務めた会社を退職しました。プログラミングスクールでHTML/CSS,JavaCcript,Vue.js,PHP,Pythonなどのフロントエンドを重点的に学びました現在はAWSやDokerを勉強しながら求職中です。",
      },
    ],
  }),
};
</script>