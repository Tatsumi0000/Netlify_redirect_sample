<template>
  <v-snackbar
    color="blue"
    :timeout="0"
    v-model="daialogFlag"
    :multi-line="multiLine"
    auto-height
    top
  >
    サーバをNetlifyからロリポップへ移行するため、URLが変更となります。
    <v-btn text @click="redirectStart()">新しいURLへ</v-btn>
  </v-snackbar>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "RedirectPopup",
  data() {
    return {
      daialogFlag: true,
      multiLine: true
    };
  },
  created() {},
  mounted() {},
  methods: {
    redirectStart() {
      if (process.browser) {
        location.href = "https://covid19-miyazaki.digick.jp/";
      }
    }
  }
});
</script>


