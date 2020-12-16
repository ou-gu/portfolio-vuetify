<template>
  <div id="about">
    <v-container fluid>
      <v-card width="100vw" class="pa-4">
        <v-card-title class="justify-center display-1 font-italic">
          About me
        </v-card-title>
        <v-timeline>
          <v-timeline-item
            v-for="(year, i) in years"
            :key="i"
            :color="year.color"
            small
          >
            <template v-slot:opposite>
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
        year: "2014-15",
        title: "工学院大学",
        content: "野球サークルでのびのび遊んでました",
      },
      {
        color: "green",
        year: "2014-15",
        title: "工学院大学",
        content: "野球サークルでのびのび遊んでました",
      },
      {
        color: "pink",
        year: "2014-15",
        title: "工学院大学",
        content: "野球サークルでのびのび遊んでました",
      },
      {
        color: "amber",
        year: "2014-15",
        title: "工学院大学",
        content: "野球サークルでのびのび遊んでました",
      },
      {
        color: "orange",
        year: "2014-15",
        title: "工学院大学",
        content: "野球サークルでのびのび遊んでました",
      },
    ],
  }),
};
</script>