<template>
  <div id="about">
    <v-container fluid>
      <v-card width="100vw" class="pa-4">
        <v-card-title class="justify-center display-1 font-italic">
          About me
        </v-card-title>

        <div class="px-2">
          <v-card-title primary-title>
            <div class="headline">Activity</div>
          </v-card-title>

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
    years: [
      {
        color: "cyan",
        year: "1992-7-11",
        title: "福建省で誕生",
        content:
          "中国の農村部で生まれました、8歳まで過ごしていました。親戚が多くとても活発な子でした。",
      },
      {
        color: "pink",
        year: "2012-2014",
        title: "工学院大学",
        content:
          "大学では環境工学を勉強していました、逆浸透膜（RO）の研究に携わっていました。環境問題に興味があり将来的には水質浄化などのプロジェクトに携わりたいと考えています。",
      },
      {
        color: "amber",
        year: "2016-2020",
        title: "プラントエンジニアとして就職",
        content:
          "中国や韓国の半導体メーカーと一緒に工場を立ち上げる仕事をしていました。施工管理、設計や装置の試運転業務に携わっていました。",
      },
      {
        color: "grey",
        year: "2020-10",
        title: "無職",
        content:
          "場所に縛られず働けるITエンジニアに憧れて、4年半務めた会社を退職しました。現在はHTML/CSS,JavaCcript,Vue.js,PHP,Pythonの勉強を学んでいます。",
      },
    ],
    activities: [
      {
        text: "好きなこと",
        subtext:
          "食べることが大好きで、特に甘いもの好きで暇なときにタルトを自分で焼いたりしてます。学生時代と比較して10キロも太ってしまったので気を付ける必要があります。",
        icon: "mdi-cake-variant",
      },
      {
        text: "ボルダリング",
        subtext:
          "体を動かすのが好きで、いろんなスポーツをします。最近のマイブームはボルダリングです、次の日に謎箇所の筋肉痛がよくあります",
        icon: "mdi-image-filter-hdr",
      },
      {
        text: "やりたい事",
        subtext:
          "世界中を旅したい、特に東南アジアなど自然が多く残ってる常夏の島々に行きたいと考えています",
        icon: "mdi-airplane-takeoff",
      },
      {
        text: "プログラミング",
        subtext:
          "農業×ITを実現させてみたいです、これから人口増加に伴い食料不足が問題となっています。現在就農人口が高齢化進んでいるためITで解決できないかを模索してす",
        icon: "mdi-iframe",
      },
      {
        text: "今後の展望",
        subtext:
          "中国生まれ、日本育ちとして両国の関係に何かしらいい影響を与えられる人材になりたいと考えています。",
        icon: "mdi-binoculars",
      },
    ],
  }),
};
</script>