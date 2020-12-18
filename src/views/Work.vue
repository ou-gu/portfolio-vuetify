<template>
  <div id="work">
    <v-container fluid>
      <v-card width="100vw">
        <v-row justify="center" align-content="center">
          <v-col cols="12" xs="7" sm="10" md="10" offset-xl="1">
            <h1 class="pagetitle display-3 font-weight-bold mt-8 mb-8">
              Work
            </h1>
          </v-col>
          <v-col
            v-for="card in cards"
            :key="card.name"
            :cols="card.flex.cols"
            :sm="card.flex.sm"
            :md="card.flex.md"
            class="pa-10"
          >
            <a :href="card.redirect_url">
              <v-hover v-slot:default="{ hover }">
                <v-card :elevation="hover ? 12 : 4">
                  <v-img
                    :src="card.src"
                    class="white--text align-end"
                    gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                    height="250px"
                  >
                    <v-card-title v-text="card.title"></v-card-title>
                    <v-card-text v-text="card.skill"></v-card-text>
                  </v-img>
                </v-card>
              </v-hover>
            </a>
          </v-col>
        </v-row>
      </v-card>

      <v-card py-6 px-5>
        <v-row justify="center" align-content="center">
          <v-col cols="12" xs="7" sm="10" md="10" offset-xl="1">
            <h1 class="pagetitle display-3 font-weight-bold mt-8 mb-8">
              Skills
            </h1>
          </v-col>
          <v-col
            xs="12"
            sm="6"
            md="4"
            v-for="skill in skills"
            :key="skill.title"
          >
            <template>
              <v-hover>
                <v-card
                  slot-scope="{ hover }"
                  class="text-xs-center ma-4"
                  :class="`elevation-${hover ? 12 : 4}`"
                  color="blue darken-2"
                >
                  <v-card-title>
                    <div class="mx-auto">
                      <v-progress-circular
                        :value="skill.value"
                        :color="skill.color"
                        :rotate="-90"
                        width="40"
                        size="200"
                      >
                        {{ skill.value }}
                      </v-progress-circular>
                    </div>
                  </v-card-title>

                  <v-card-actions>
                    <v-layout justify-space-around>
                      <div class="headline">
                        <template>
                          <span
                            :color="skill.color"
                            :class="`${skill.color}--text`"
                            class="subtitle-1"
                          >
                            <v-icon size="25" color="white">
                              {{ skill.icon }}
                            </v-icon>
                            {{ skill.title }}
                          </span>
                        </template>
                      </div>
                    </v-layout>
                  </v-card-actions>
                </v-card>
              </v-hover>
            </template>
          </v-col>
        </v-row>
      </v-card>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: [
        {
          title: "Portfolio Page",
          skill: "Vue.js",
          src: require("@/assets/img/work-05.png"),
          flex: { cols: 12, sm: 6, md: 4 },
        },
        {
          title: "Starbucks copy site",
          skill: "HTML/CSS,JavaScript",
          src: require("@/assets/img/work-01.png"),
          flex: { cols: 12, sm: 6, md: 4 },
        },
        {
          title: "Blog",
          skill: "Wordpress,PHP",
          src: require("@/assets/img/work-02.png"),
          flex: { cols: 12, sm: 6, md: 4 },
        },
        {
          title: "Google Map API",
          skill: "API",
          src: require("@/assets/img/work-03.png"),
          flex: { cols: 12, sm: 6, md: 4 },
        },
        {
          title: "E-Commerce",
          skill: "Bootstrap",
          src: require("@/assets/img/work-04.png"),
          flex: { cols: 12, sm: 6, md: 4 },
        },
      ],
      skills: [
        {
          title: "HTML&CSS",
          value: 0,
          absoluteValue: 50,
          color: "white",
          icon: "mdi-language-html5",
          show: false,
        },
        {
          title: "JavaScript",
          value: 0,
          absoluteValue: 30,
          color: "white",
          icon: "mdi-language-javascript",
          show: false,
        },
        {
          title: "PHP",
          value: 0,
          absoluteValue: 20,
          color: "white",
          icon: "mdi-language-php",
          show: false,
        },
        {
          title: "Wrodpress",
          value: 0,
          absoluteValue: 10,
          color: "white",
          icon: "mdi-wordpress",
          show: false,
        },
        {
          title: "Git hub",
          value: 0,
          absoluteValue: 20,
          color: "white",
          icon: "mdi-github",
          show: false,
        },
        {
          title: "Vue.js",
          value: 0,
          absoluteValue: 10,
          color: "white",
          icon: "mdi-vuejs",
          show: false,
        },
        {
          title: "Python",
          value: 0,
          absoluteValue: 10,
          color: "white",
          icon: "mdi-language-python",
          show: false,
        },
        {
          title: "Chinese",
          value: 0,
          absoluteValue: 90,
          color: "white",
          icon: "mdi-panda",
          show: false,
        },
        {
          title: "Muscle training",
          value: 0,
          absoluteValue: 40,
          color: "white",
          icon: "mdi-weight-lifter",
          show: false,
        },
        {
          title: "You Tube",
          value: 0,
          absoluteValue: 100,
          color: "white",
          icon: "mdi-youtube",
          show: false,
        },
        {
          title: "E A T",
          value: 0,
          absoluteValue: 100,
          color: "white",
          icon: "mdi-silverware-clean",
          show: false,
        },
      ],
      interval: {},
      expand: false,
    };
  },
  beforeDestroy() {
    clearInterval(this.interval);
  },
  mounted() {
    let timesRun = 0;
    this.interval = setInterval(() => {
      if (timesRun === 10) {
        clearInterval(this.interval);
        return;
      }
      timesRun += 1;
      this.skills.forEach((skill) => {
        if (skill.absoluteValue !== skill.value) {
          skill.value += 10;
        }
      });
    }, 300);
  },
};
</script>