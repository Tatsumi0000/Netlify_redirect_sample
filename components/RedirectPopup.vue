<template>
  <v-row justify="center">
    <v-daialog v-if="daialogFlag" max-width="290">
      <v-card>
        <v-card-title class="headline">サーバ移転のお知らせをのタイトルだよーん</v-card-title>
        <v-card-text>ここにお知らせの詳細を書くよーん</v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="blue darken-1" text @click="daialog = false">合点承知の助</v-btn>
        </v-card-actions>
      </v-card>
    </v-daialog>
  </v-row>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "RedirectPopup",
  data() {
    return {
      daialogTime: 3,
      daialogFlag: false
    };
  },
  created() {
    setInterval(() => {
      this.daialogTime--;
      if (this.daialogTime == 0) {
        this.daialogFlag = true;
      }
    }, 1000);
  },
  mounted() {},
  methods: {}
});
</script>

<style scoped>
.popup {
  z-index: 9999;
  width: 40%;
  height: 40%;
}
</style>
